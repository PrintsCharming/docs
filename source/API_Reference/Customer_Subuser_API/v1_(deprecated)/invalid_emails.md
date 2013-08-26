---
layout: page
weight: 0
title: Invalid Emails
navigation:
   show: true
---

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser we are retrieving invalid emails from

</td>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *get*

</td>
<td markdown="1">
This will allow you to retrieve the invalid emails for the specified subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be set to 1

</td>
<td markdown="1">
Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.invalidemails.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
{% endcodeblock %}
  <h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<invalidemails>
   <invalidemail>
      <email>isaac@hotmail.comm</email>
      <reason>Mail domain mentioned in email address is unknown</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
   <invalidemail>
      <email>isaac@hotmail</email>
      <reason>Bad Syntax</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
   <invalidemail>
      <email>isaac@example.com</email>
      <reason>Known bad domain</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
</invalidemails>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/user.invalidemails.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date=
{% endcodeblock %}
  <h3>Response</h3>
  
{% codeblock lang:javascript %}
[
  {
    "email": "isaac@hotmail.comm",
    "reason": "Mail domain mentioned in email address is unknown",
    "created": "2009-06-01 19:41:39"
  },
  {
    "email": "isaac@hotmail",
    "reason": "Bad Syntax",
    "created": "2009-06-01 19:41:39"
  },
  {
    "email": "isaac@example.com",
    "reason": "Known bad domain",
    "created": "2009-06-01 19:41:39"
  }
]
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Delete Invalid Emails {% endanchor %}
 Since SendGrid does not deliver to invalid emails, users can remove invalid emails from their list at any time if re-delivery to a spam reported address is desired.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser we are retrieving invalid emails from

</td>
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *delete*

</td>
<td markdown="1">
This will allow you to delete a invalid email for the specified subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a invalid email

</td>
<td markdown="1">
You must specify the invalid emails to remove

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/user.invalidemails.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=invalidemail@example.com
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




### JSON Request



{% codeblock %}
https://sendgrid.com/api/user.invalidemails.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=invalidemail@example.com
{% endcodeblock %}
<div class="tab-pane active" id="delete-json">
   <h3>Call</h3>
  
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

