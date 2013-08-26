---
layout: page
weight: 0
title: Subuser Spam Reports
navigation:
   show: true
---

{% anchor h2 %} Retrieve Spam Reports {% endanchor %}



{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.spamreports.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<spamreports>
   <spamreport>
      <email>email1@domain.com</email>
      <created>2009-06-10 12:40:30</created>
   </spamreport>
   <spamreport>
      <email>email2@domain2.com</email>
      <created>2009-06-10 12:40:30</created>
   </spamreport>
</spamreports>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/user.spamreports.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
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


{% anchor h2 %} Delete Spam Reports {% endanchor %}
 Since SendGrid does not deliver to spam reported addresses, users can remove spam reports from their list at any time if re-delivery to a spam reported address is desired.


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.spamreports.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=spamreport@domain.com
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
https://sendgrid.com/api/user.spamreports.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=spamreport@domain.com
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

