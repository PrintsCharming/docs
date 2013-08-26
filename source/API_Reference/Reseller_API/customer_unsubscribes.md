---
layout: page
weight: 0
title: Customer Unsubscribes
navigation:
   show: true
---

{% anchor h2 %} Retrieve Unsubscribes {% endanchor %}


Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *get*|This will allow you to retrieve the unsubscribes for the specified customer|
|date|No|Must be set to 1|Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS|
|method|Yes|Must be set to *unsubscribes*|Allows you to access unsubscribe functionality|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=get&date=
{% endcodeblock %}
<h3>Response</h3>

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




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=get&date=
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "email": "email1@domain.com",
    "created": "2009-06-01 19:41:39"
  },
  {
    "email": "email2@domain2.com",
    "created": "2009-06-01 19:41:39"
  }
]
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Delete Unsubscribes {% endanchor %}


Since SendGrid does not deliver to unsubscribe addresses, users can remove unsubscribes from their list at any time if re-delivery to an unsubscribed address is desired.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *delete*|This will allow you to delete an unsubscribe record for the specified customer|
|email|No|Must be an unsubscribe record|You must specify the unsubscribe record to remove|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=delete&email=unsubscribe@sample.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>Email does not exist</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=delete&email=unsubscribe@sample.com
{% endcodeblock %}
<h3>Response: Success</h3>

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




</div>
</div>

* * * * *


{% anchor h2 %} Add Unsubscribes {% endanchor %}


Add unsubscribe email records to their account if they need to stop sending email messages to a specific recipient.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Customer must be registered under your account|The customer we are retrieving unsubscribes from|
|task|Yes|Must be set to *add*|This will allow you to add an unsubscribe record for the specified customer|
|email|No|Must be an unsubscribe record|You must specify the unsubscribe record to add|

{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=add&email=unsubscribe@sample.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>Email already exists</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=customer@example.com&task=add&email=unsubscribe@sample.com
{% endcodeblock %}
<h3>Response: Success</h3>

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




</div>
</div>

