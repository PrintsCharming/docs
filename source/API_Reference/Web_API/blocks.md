---
layout: page
weight: 0
title: Blocks
navigation:
  show: true
---

This endpoint allows you to retrieve and delete entries in the Blocks list.


{% anchor h2 %} get {% endanchor %}
Retrieve a list of Blocks with addresses and response codes, optionally with dates.

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
Retrieve the timestamp of the Block records. It will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS

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
Number of days in the past for which to retrieve blocks (includes today)

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
The start of the date range for which to retrieve blocks.

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
The end of the date range for which to retrieve blocks.

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
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/blocks.get.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:12:12",
    "reason": "550 Access denied...04d52d35b93501d500a9bca895ddad5cddd1a9f8486c89ace8c5e959398198cd49cd58288c9d11313975284d852811... (throttled)",
    "email": "example@juno.com"
  },
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:21:29",
    "reason": "Connection timed out",
    "email": "example2@band.la"
  },
  {
    "status": "4.0.0",
    "created": "2012-09-02 00:25:33",
    "reason": "Unable to resolve MX record for exampledomain.com: nxdomain",
    "email": "example3@exampledomain.com"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/blocks.get.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;date=1
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<blocks>
   <block>
      <email>email1@domain.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com</reason>
      <created>2009-06-10 12:40:30</created>
   </block>
   <block>
      <email>email2@domain2.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com</reason>
      <created>2009-08-01 10:16:30</created>
   </block>
</blocks>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}
Delete an address from the Block list.

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
Email block address to remove

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/blocks.delete.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
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
https://sendgrid.com/api/blocks.delete.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;email=emailToDelete@domain.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
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

