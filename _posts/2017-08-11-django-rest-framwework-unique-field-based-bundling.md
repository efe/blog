---
layout: post
title: "DRF and Unique Field Based Bundling"
---

Django Rest Framework is very powerful API framework with built-in class based views and serializers. Despite of having numerous features, DRF lets you to customize deeply. In this post, I would like to serialize items within json object instead of json array.

Here is the traditional listing response. There are list of book items which are compound in list.

```json
[
    {
        "id": 1,
        "title": "The Man in the High Castle",
        "writer": "Philip K. Dick",
        "isbn": "9780679740674"
    },
    {
        "id": 2,
        "title": "B Is for Beer",
        "writer": "Tom Robbins",
        "isbn": "9780061687273"
    },
    {
        "id": 3,
        "title": "Tales of Nasrettin Hoca",
        "writer": "Aziz Nesin",
        "isbn": "9789759548100"
    }
]
```

However, API consumer sometimes would like to go over the response more easily. Imagine this scenario, Frontend would like to reach writer of the book immediately with it's ISBN. In traditional way, FE will iterate over all list items and look it's ISBN is correct or not. If so, It returns value of writer keyword in book object.

In this case, Bundle like below will be more useful for the API consumer. There are items bundled with-in their ISBN numbers.

```json
{
    "9780679740674": {
        "id": 1,
        "title": "The Man in the High Castle",
        "writer": "Philip K. Dick"
    },
    "9780061687273": {
        "id": 2,
        "title": "B Is for Beer",
        "writer": "Tom Robbins"
    },
    "9789759548100": {
        "id": 3,
        "title": "Tales of Nasrettin Hoca",
        "writer": "Aziz Nesin"
    }
}
```

We can easily implement a mixin and use it with `ModelSerializer`. In the mixin, We just need to override `to_representation()` method of `ModelSerializer` and `ListSerializer`.

```python
# books/mixins.py

from rest_framework.serializers import ListSerializer as DRFListSerializer


class UniqueFieldMixin(object):
    unique_lookup_field = 'id'

    def to_representation(self, instance):
        bundle = super().to_representation(instance)

        lookup_value = str(bundle.get(self.unique_lookup_field))
        bundle.pop(self.unique_lookup_field)

        return {lookup_value: bundle}


    class ListSerializer(DRFListSerializer):
        def to_representation(self, data):
            from collections import OrderedDict

            context = OrderedDict()

            for item in data:
                context.update(self.child.to_representation(item))

            return context

        @property
        def data(self):
            return super(DRFListSerializer, self).data
```

Set the field which will be key of the bundle in `unique_lookup_field`. Use the `UniqueFieldMixin.ListSerializer` as a `list_serializer_class`.

```python
# books/serializers.py

from books.mixins import UniqueFieldMixin
from books.models import Book
from rest_framework.serializers import ModelSerializer


class BookSerializer(UniqueFieldMixin, ModelSerializer):
    unique_lookup_field = 'isbn'

    class Meta:
        model = Book
        fields = ('id', 'title', 'writer', 'isbn')
        list_serializer_class = UniqueFieldMixin.ListSerializer
```

That's it!
