---
layout: page
weight: 0
title: Subuser Unsubscribes
navigation:
   show: true
---

{% anchor h2 %} Retrieve Unsubscribes {% endanchor %}
 Note that you can use *either* the days parameter *or* the start_date and end_date parameter.

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
The subuser we are retrieving unsubscribes from

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
This will allow you to retrieve the unsubscribes for the specified subuser

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
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date= {% endcodeblock %}

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


</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=get&date= {% endcodeblock %}

### Response


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
The subuser we are retrieving unsubscribes from

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
This will allow you to delete an unsubscribe record for the specified subuser

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
Must be an unsubscribe record

</td>
<td markdown="1">
You must specify the unsubscribe record to remove

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success


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

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=delete&email=unsubscribe@sample.com {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} Add Unsubscribes {% endanchor %}
 Add unsubscribe email records to their account if they need to stop sending email messages to a specific recipient.

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
The subuser we are retrieving unsubscribes from

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
Must be set to *add*

</td>
<td markdown="1">
This will allow you to add an unsubscribe record for the specified subuser

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
Must be an unsubscribe record

</td>
<td markdown="1">
You must specify the unsubscribe record to add

</td>
</tr>
</tbody>
</table>
{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="add-xml">
### Call

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=add&email=unsubscribe@sample.com {% endcodeblock %}

### Response: Success


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

{% codeblock %} https://sendgrid.com/api/user.unsubscribes.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&task=add&email=unsubscribe@sample.com {% endcodeblock %}

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


</div>
</div>

