---
layout: page
weight: 0
title: Recipients
navigation:
  show: true
---

This module allows you to manage which lists are assigned to marketing email.


{% anchor h2 %} add {% endanchor %}


Assign a List to a Marketing Email.

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
list

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The name of the list to assign to the marketing email

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The name of the marketing email

</td>
</tr>
</tbody>
</table>
{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/recipients/add.json?name=SendGrid%20NL%20Test2&list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/recipients/add.xml?name=SendGrid%20NL%20Test2&list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} get {% endanchor %}


Get all lists assigned to a particular marketing email

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
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The name of the marketing email for which to retrieve lists.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/recipients/get.json?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

          <h3>Response: Success</h3>

{% codeblock lang:javascript %}
[
  {
    "list": "Training Contacts"
  }
]
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
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/recipients/get.xml?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<lists>
   <list>
      <list>Training Contacts</list>
   </list>
</lists>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Remove assigned lists from marketing email

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
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an existing marketing email

</td>
<td markdown="1">
To marketing email from which the list will be unassigned.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
list

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an existing Recipient List.

</td>
<td markdown="1">
Remove this list from the marketing email

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/delete.json?name=SendGrid%20NL%20Test1&list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/delete.xml?name=SendGrid%20NL%20Test1&list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

