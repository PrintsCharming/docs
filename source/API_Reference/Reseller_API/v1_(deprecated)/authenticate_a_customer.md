---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---

Authenticate a customer on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.

|Parameter|Required|Requirements|
|:--------|:-------|:-----------|
|user|Yes|Customer that is registered under your account.|
|password|Yes|Password the customer submitted.|
|method|Yes|Must be set to *auth*. Allows you to access authentication functionality|

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com&password=theirsubmittedpassword&method=aut
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
result><message>success</message></result>
{% endcodeblock %}



### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com&password=theirsubmittedpassword&method=aut
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}



