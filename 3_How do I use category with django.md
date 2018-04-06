I am going to use category with django blog system.

### models.py
```python
class Category(models.Model):
    name = models.CharField('Category', max_length=255)
    description = models.TextField('Description', blank=True)
    created_at = models.DateTimeField(default=timezone.now)
    def __str__(self):
        return self.name
class Post(models.Model):
    author = models.ForeignKey('auth.User')
    title = models.CharField(max_length=200)
    text = models.TextField()
    category = models.ForeignKey(Category, verbose_name='category', on_delete=models.PROTECT, null=True)
    image = models.FileField(upload_to="%Y/%m/", null=True, blank=True)
    created_date = models.DateTimeField(default=timezone.now)
    published_date = models.DateTimeField(blank=True, null=True)
    def publish(self):
        self.published_date = timezone.now()
        self.save()
    def get_absolute_url(self):
        return reverse("post_detail", kwargs={'pk':self.pk})
    def __str__(self):
        return self.title
```
### views.py
```python
class CategoryView(ListView):
    model = Post
    def get_queryset(self):
        category_name = self.kwargs['category']
        self.category = Category.objects.get(name=category_name)
        queryset = super().get_queryset().filter(category=self.category, published_date__lte=timezone.now()).order_by('-published_date')
        return queryset
    def get_context_data(self, *args, **kwargs):
        context = super().get_context_data(*args, **kwargs)
        context['categories'] = Category.objects.all()
        return context
```
### urls.py
```html
urlpatterns = [
    ...
    url(r'^category/(?P<category>.*)/$', views.CategoryView.as_view(), name='category'),
]
post_list.html
<!-- Categories Widget -->
<div class="card my-4">
<h5 class="card-header">Categories</h5>
<div class="card-body">
    <div class="row">
        {% for category in categories %}
        <div class="col-lg-6">
            <ul class="list-unstyled mb-3">
                <li>
                    <a class="btn btn-dark" href="{% url 'category' category.name %}">
                        {{ category.name }}
                    </a>
                </li>
            </ul>
        </div>
        {% endfor %}
    </div>
</div>
</div>
```