---
layout: page
weight: 0
title: Customer Unsubscribes
navigation:
   show: true
---

{% anchor h2 %} Retrieve Unsubscribes {% endanchor %}


Note that you can use *either* the days parameter *or* the start_date and end_date parameter.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *get*|This will allow you to retrieve the unsubscribes for the specified customer|
|date|No|Must be set to 1|Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS|
|method|Yes|Must be set to *unsubscribes*|Allows you to access unsubscribe functionality|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=get&date= {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<unsubscribes>
   <unsubscribe>
      <email>email1@domain.com</email>
      <created>2009-06-10 12:40:30</created>
   </unsubscribe>
   <unsubscribe>
      <email>email2@domain2.com</email>
      <created>2009-06-10 12:40:30</created>
   </unsubscribe>
</unsubscribes>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=get&date= {% endcodeblock %}

### Response



* * * * *


{% anchor h2 %} Delete Unsubscribes {% endanchor %}


Since SendGrid does not deliver to unsubscribe addresses, users can remove unsubscribes from their list at any time if re-delivery to an unsubscribed address is desired.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *delete*|This will allow you to delete an unsubscribe record for the specified customer|
|email|No|Must be an unsubscribe record|You must specify the unsubscribe record to remove|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=delete&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success

{% codeblock %} result\><message>success</message></result> {% endcodeblock %}

### Response: Error

{% codeblock %} result\><message>Email does not exist</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=delete&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "Email does not exist"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Add Unsubscribes {% endanchor %}


Add unsubscribe email records to their account if they need to stop sending email messages to a specific recipient.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *add*|This will allow you to add an unsubscribe record for the specified customer|
|email|No|Must be an unsubscribe record|You must specify the unsubscribe record to add|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=add&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success

{% codeblock %} result\><message>success</message></result> {% endcodeblock %}

### Response: Error

{% codeblock %} result\><message>Email already exists</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=add&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "Email already exists"
}
{% endcodeblock %}

