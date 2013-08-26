---
layout: page
weight: 0
title: Subuser Bounces
navigation:
   show: true
---

{% anchor h2 %} Retrieve Bounces {% endanchor %}
 Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.bounces.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<bounces>
   <bounce>
      <email>email1@domain.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com</reason>
      <created>2009-06-10 12:40:30</created>
   </bounce>
   <bounce>
      <email>email2@domain2.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com</reason>
      <created>2009-06-10 12:40:30</created>
   </bounce>
</bounces>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/user.bounces.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=1
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:javascript %}
[
  {
    "email": "email1@domain.com",
    "status": "5.1.1",
    "reason": "host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com",
    "created": "2009-06-01 19:41:39"
  },
  {
    "email": "email2@domain2.com",
    "status": "5.1.1",
    "reason": "host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com",
    "created": "2009-06-01 19:41:39"
  }
]
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Delete Bounces {% endanchor %}
 Since SendGrid does not re-deliver to bounced addresses, users can remove bounces from their list at any time if redelivery to a bounced address is desired.


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.bounces.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=bounce@example.com
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
https://sendgrid.com/api/user.bounces.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=bounce@example.com
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

