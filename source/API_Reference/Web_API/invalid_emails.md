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
date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be set to 1

</td>
<td markdown="1">
Retrieve the timestamp of the invalid email records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

</td>
</tr>
<tr markdown="1">
<td markdown="1">
days

</td>
<td markdown="1">
No

</td>
<td markdown="1">
If specified, must be an integer greater than 0

</td>
<td markdown="1">
Number of days in the past for which to retrieve invalid emails (includes today)

</td>
</tr>
<tr markdown="1">
<td markdown="1">
start\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-MM-DD format and be earlier than the end\_date parameter.

</td>
<td markdown="1">
The start of the date range for which to retrieve invalid emails.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
end\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-MM-DD format and be later than the start\_date parameter.

</td>
<td markdown="1">
The end of the date range for which to retrieve invalid emails.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
limit

</td>
<td markdown="1">
No

</td>
<td markdown="1">
some integer

</td>
<td markdown="1">
Optional field to limit the number of results returned.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
offset

</td>
<td markdown="1">
No

</td>
<td markdown="1">
some integer

</td>
<td markdown="1">
Optional beginning point in the list to retrieve from.

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
email address eg testing@example.com

</td>
<td markdown="1">
Optional email addresses to search for.

</td>
</tr>
</tbody>
</table>
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
email

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid user account email

</td>
<td markdown="1">
Email Invalid Email address to remove

</td>
</tr>
<tr markdown="1">
</tr>
</tbody>
</table>
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

