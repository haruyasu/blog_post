I am going to use pagination with django class based generic ListViews.

Just setting the paginate_by

### view.py
```python
from django.views.generic import (TemplateView, ListView, DetailView, CreateView, UpdateView, DeleteView)
class PostListView(ListView):
    model = Post
    paginate_by = 3
    def get_queryset(self):
        return Post.objects.filter(published_date__lte=timezone.now()).order_by('-published_date')
```

### post_list.html
```html
<!-- Pagination -->
{% if is_paginated %}
<nav class="my-4">
    <ul class="pagination pagination-circle pg-darkgrey justify-content-center mb-0">
        {% if page_obj.has_previous %}
            <li class="page-item">
                <a class="page-link" href="?page={{ page_obj.previous_page_number }}" tabindex="-1">Previous</a>
            </li>
        {% endif %}
        {% for link_page in page_obj.paginator.page_range %}
            {% if link_page == page_obj.number %}
                <li class=" page-item active">
                    <a class="page-link" href="#" tabindex="-1">{{ link_page }}</a>
                </li>
            {% else %}
                <li class="page-item">
                    <a class="page-link" href="?page={{ link_page }}">{{ link_page }}</a>
                </li>
            {% endif %}
        {% endfor %}
        {% if page_obj.has_next %}
            <li class="page-item">
                <a class="page-link" href="?page={{ page_obj.next_page_number }}">Next</a>
            </li>
        {% endif %}
    </ul>
</nav>
{% endif %}
<!-- Pagination -->
```