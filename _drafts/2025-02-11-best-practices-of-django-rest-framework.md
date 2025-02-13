---
layout: post
title: "Best practices of Django Rest Framework"
---

I've been developing APIs with [Django Rest Framework](https://www.django-rest-framework.org/) for 8 years. I would like to share my experiences in this blogpost.

## Do not use viewset

Viewsets are higher level abstractions of [Generic API Views](https://www.django-rest-framework.org/api-guide/generic-views/). It automtically creates   

## Use drf-spectacular for auto generated documentation

## Have default Limit Offset pagination as default

### set maximum page size

## Have exception handler

## Enable filter backends

### django_filters.rest_framework.DjangoFilterBackend

### rest_framework.filters.OrderingFilter

## Have throttling

## Have default permission class

## Use HiddenInputField

## Do not write business logic in serializers

## Use multiple serializers if needed

## Validate in model

## Validate fields first then models

## Separate create and update serializers by functionalities

## Use ActionBasedSerializer if necessary

