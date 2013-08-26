---
layout: page
weight: 0
title: Bounces
navigation:
  show: true
---

This endpoint allows you to retrieve and delete entries in the Bounces list.


{% anchor h2 %} get {% endanchor %}


Retrieve a list of bounces with addresses and response codes, optionally with dates.

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
Retrieve the timestamp of the bounce records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

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
Number of days in the past for which to retrieve bounces (includes today)

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
The start of the date range for which to retrieve bounces.

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
The end of the date range for which to retrieve bounces.

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
type

</td>
<td markdown="1">
No

</td>
<td markdown="1">
hard or soft

</td>
<td markdown="1">
choose the type of bounce to search for.

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
https://sendgrid.com/api/bounces.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
{% endcodeblock %}
      <h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "status": "4.0.0",
    "created": "2011-09-16 22:02:19",
    "reason": "Unable to resolve MX host sendgrid.ne",
    "email": "esting@sendgrid.ne"
  },
  {
    "status": "4.0.0",
    "created": "2011-09-19 17:47:15",
    "reason": "Connection timed out",
    "email": "rawest@gmail.co"
  },
  {
    "status": "5.1.1",
    "created": "2011-10-17 11:07:10",
    "reason": "550 5.1.1 The email account that you tried to reach does not exist. Please try double-checking the recipient's email address for typos or unnecessary spaces. Learn more at http://mail.google.com/support/bin/answer.py?answer=6596 z10si838244anz.171 ",
    "email": "claims@msp.org"
  },
  {
    "status": "5.7.1",
    "created": "2011-10-26 23:06:22",
    "reason": "550 5.7.1 <info@bnl.co.uk>... Relaying denied. Proper authentication required. ",
    "email": "info@bnl.co.uk"
  },
  {
    "status": "5.7.1",
    "created": "2011-12-01 01:45:55",
    "reason": "554 5.7.1 <richard@hengseng.com>: Relay access denied ",
    "email": "richard@hengseng.com"
  },
  {
    "status": "550",
    "created": "2012-06-01 14:10:15",
    "reason": "550 support.sendgrid.net [74.63.202.100] is currently not permitted to relay through this server. Perhaps you have not logged into the pop/imap server in the last 30 minutes or do not have SMTP Authentication turned on in your email client. ",
    "email": "test@brandonmwest.com"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/bounces.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&date=1
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
      <created>2009-08-01 10:16:30</created>
   </bounce>
</bounces>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Delete an address from the Bounce list. Please note that if no parameters are specified the ENTIRE list will be deleted.

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
start\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Date must be in YYYY-mm-dd format and be before the end\_date parameter

</td>
<td markdown="1">
Optional date to start deleting from.

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
Date must be in YYYY-mm-dd format and be after the start\_date parameter

</td>
<td markdown="1">
Optional date to end deleting from.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
type

</td>
<td markdown="1">
No

</td>
<td markdown="1">
hard or soft

</td>
<td markdown="1">
choose the type of bounce to be removed.

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
Must be a valid user account email

</td>
<td markdown="1">
Email bounce address to remove

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
https://sendgrid.com/api/bounces.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
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
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/bounces.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=emailToDelete@domain.com
{% endcodeblock %}
	<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
  success
@nodes
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


{% anchor h2 %} Count {% endanchor %}


||
|Parameter|Required|Requirements|Description|
|start\_date|No|Date must be in YYYY-mm-dd format and be before the end\_date parameter|Optional date to start counting from.|
|end\_date|No|Date must be in YYYY-mm-dd format and be after the start\_date parameter|Optional date to end counting from.|
|type|No|hard or soft|choose the type of bounce to search for.|

{% xmljsontabs count %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="count-json">
### Call



{% codeblock %}
https://sendgrid.com/api/bounces.count.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %} 
	<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "count": "4"
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
<div markdown="1" class="tab-pane" id="count-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/bounces.count.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
	<h3>Response: Success</h3>


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
   @nodes
</result>

{% endcodeblock %}




#### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

