---
layout: page
weight: 0
title: Django
navigation:
  show: true
---

There is more detailed information about [sending email with Django](https://docs.djangoproject.com/en/dev/topics/email/) on the Django project website.

First start by adding the following to **settings.py:** {% codeblock lang:python %} EMAIL\_HOST = 'smtp.sendgrid.net' EMAIL\_HOST\_USER = 'sendgrid\_username' EMAIL\_HOST\_PASSWORD = 'sendgrid\_password' EMAIL\_PORT = 587 EMAIL\_USE\_TLS = True {% endcodeblock %} Then to send email you can do the following: {% codeblock lang:python %} from django.core.mail import send\_mail send\_mail('Subject here', 'Here is the message.', 'from@example.com', ['to@example.com'], fail\_silently=False) {% endcodeblock %}
