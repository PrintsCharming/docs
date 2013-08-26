---
layout: page
weight: 0
title: Django
navigation:
  show: true
---

There is more detailed information about [sending email with Django](https://docs.djangoproject.com/en/dev/topics/email/) on the Django project website.

First start by adding the following to **settings.py:** {% codeblock lang:python %} EMAIL_HOST = 'smtp.sendgrid.net' EMAIL_HOST_USER = 'sendgrid_username' EMAIL_HOST_PASSWORD = 'sendgrid_password' EMAIL_PORT = 587 EMAIL_USE_TLS = True {% endcodeblock %} Then to send email you can do the following: {% codeblock lang:python %} from django.core.mail import send_mail send_mail('Subject here', 'Here is the message.', 'from@example.com', ['to@example.com'], fail_silently=False) {% endcodeblock %}
