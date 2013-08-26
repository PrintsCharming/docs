---
layout: page
weight: 0
title: Spam Reports
navigation:
  show: true
---

Retrieve and delete entries in the Spam Reports list.


{% anchor h2 %} get {% endanchor %}



{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.get.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "ip": "174.36.80.219",
    "email": "example@aol.com",
    "created": "2009-12-06 15:45:08"
  },
  {
    "ip": "74.63.202.105",
    "email": "example2@yahoo.com",
    "created": "2009-12-08 07:43:01"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.get.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<spamreports>
   <spamreport>
      <ip>174.36.80.219</ip>
      <email>example@aol.com</email>
      <created>2009-12-06 15:45:08</created>
   </spamreport>
   <spamreport>
      <ip>74.63.202.105</ip>
      <email>example2@yahoo.com</email>
      <created>2009-12-08 07:43:01</created>
   </spamreport>
</spamreports>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Delete an address from the Spam Reports list.


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/spamreports.delete.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
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
https://sendgrid.com/api/spamreports.delete.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
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


 </result></result>

</div>
</div>

