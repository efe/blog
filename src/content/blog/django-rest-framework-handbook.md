---
title: "Django Rest Framework Handbook"
publishedAt: '2025-03-10'
category: 'django'
isFeatured: true
---

Over the past 10 years, I’ve built APIs with [Django Rest Framework](https://www.django-rest-framework.org/) (DRF) for a variety of industries, including analytics, e-commerce, ERP, healthcare, CMS and blockchain. In that time, I’ve developed and maintained APIs that have processed millions of requests, served thousands of users and integrated with dozens of third-party services. I’ve also contributed to open-source DRF projects, analyzed countless implementations and refined my understanding of best practices. Many of these insights were gained alongside the brilliant minds I worked with at [Hipo](https://hipolabs.com).

After 10 years, I thought it was time to share my knowledge—before I forget it all and have to relearn it myself.

## How does Django Rest Framework make you feel?

Django Rest Framework is like a [Seiko](https://en.wikipedia.org/wiki/Seiko) —efficient, crafted, effortless and [boring](https://boringtechnology.club/).

## 1. Do not use viewset

Viewsets are higher level abstractions of [Generic API Views](https://www.django-rest-framework.org/api-guide/generic-views/).

## 2. drf-spectacular for auto generated documentation

## 3. Have default Limit Offset pagination as default

### 3.1 Set maximum page size

## 5. Have exception handler

## 6. Enable filter backends

- `django_filters.rest_framework.DjangoFilterBackend`

`django_filters.rest_framework.DjangoFilterBackend`

- `rest_framework.filters.OrderingFilter`

## 7. Have throttling

## 8. Have default permission class

## 9. Use HiddenInputField

## 10. Do not write business logic in serializers

## 11. Use multiple serializers if needed

## 12. Validate in model

## 13. Validate fields first then models

## 14. Separate create and update serializers by functionalities

## 15. Use ActionBasedSerializer if necessary

