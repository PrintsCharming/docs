---
layout: page
weight: 0
title: Spam Reports
navigation:
  show: true
---

Retrieve and delete entries in the Spam Reports list.


{% anchor h2 %} get {% endanchor %}


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
Retrieve the timestamp of the spam report records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

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
Number of days in the past for which to retrieve spam reports (includes today)

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
The start of the date range for which to retrieve spam reports.

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
The end of the date range for which to retrieve spam reports.

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
optional beginning point in the list to retrieve from.

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
optional email addresses to search for.

</td>
</tr>
</tbody>
</table>
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
Email spam reports address to remove

</td>
</tr>
</tbody>
</table>
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

