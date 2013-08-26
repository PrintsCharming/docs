---
layout: page
weight: 0
title: Invalid Emails
navigation:
  show: true
---

This endpoint allows you to retrieve and delete entries in the Invalid Emails list.


{% anchor h2 %} get {% endanchor %}


Retrieve a list of invalid emails with addresses and response codes, optionally with dates.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/invalidemails.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}
<h3>Response</h3>


{% codeblock lang:javascript %}
[
  {
    "reason": "Known bad domain",
    "created": "2011-06-06 16:11:57",
    "email": "test@example.com"
  },
  {
    "reason": "Invalid address",
    "created": "2012-08-17 11:04:38",
    "email": "brandon"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/invalidemails.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<invalidemails>
   <invalidemail>
      <reason>Known bad domain</reason>
      <created>2011-06-06 16:11:57</created>
      <email>test@example.com</email>
   </invalidemail>
   <invalidemail>
      <reason>Invalid address</reason>
      <created>2012-08-17 11:04:38</created>
      <email>brandon</email>
   </invalidemail>
</invalidemails>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Delete an address from the Invalid Email list.


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/invalidemails.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
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




</div>
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/invalidemails.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
<result>
  success
<result>
{% endcodeblock %}



### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
  Email does not exist
@nodes
</result>

{% endcodeblock %}




</div>
</div>

