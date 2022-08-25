---
layout: post
title: "Removing 3rd Party Field in Django"
---
Once you decided to use a third party library for a model field. As time goes on, the project was evolving. Good news! You don't need the field anymore. So, What do you do? You just remove the field and dependency. But, how?

## #1: Regular Way

1. Remove field from `models.py`
2. Call `python manage.py makemigrations`
3. Call `python manage.py migrate`
4. Remove the package from `requirements.txt`

It worked well. Then, someday in future you got an error while running migrations.

## #2: 2 Step Way
