---
layout: page
weight: 0
title: Subuser Unsubscribes
navigation:
   show: true
---

{% anchor h2 %} Retrieve Unsubscribes {% endanchor %}
 Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
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
https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
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


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=unsubscribe@sample.com
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
https://sendgrid.com/api/user.unsubscribes.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=unsubscribe@sample.com
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


{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=add&email=unsubscribe@sample.com
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
https://sendgrid.com/api/user.unsubscribes.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=add&email=unsubscribe@sample.com
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

