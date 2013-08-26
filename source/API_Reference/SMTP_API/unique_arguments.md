---
layout: page
weight: 0
title: Unique Arguments
navigation:
  show: true
---

The SMTP API JSON string you to attach an unlimited number of unique arguments to your email. The arguments are used only for tracking. They can be retrieved through the [Event API]({{root_url}}/API_Reference/Webhooks/event.html) or the [Email Activity]({{root_url}}/Delivery_Metrics/email_activity.html) page.

These arguments can be added using a JSON string like this:


{% codeblock lang:javascript %}
{
  "unique_args": {
    "customerAccountNumber": "55555",
    "activationAttempt": "1"
  }
}
{% endcodeblock %}


These arguments can then be seen in posts from the SendGrid Event API. The contents of one of these posts would look something like this:

{% codeblock lang:ruby %} [email] =\> ben@sendgrid.com [test_param] =\> test_value [2nd_param] =\> 2nd_value [event] =\> processed {% endcodeblock %}

Unique Arguments will also be shown in the Email Activity tab of your account.
