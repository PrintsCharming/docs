---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---

{% anchor h2 %} Retrieve Bounces {% endanchor %}


Note that you can use *either* the days parameter *or* the start\_date and end\_date parameter.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser we are retrieving bounces from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>get</em></td>
<td align="left">This will allow you to retrieve the bounces for the specified customer subuser</td>
</tr>
<tr class="odd">
<td align="left">date</td>
<td align="left">No</td>
<td align="left">Must be set to 1</td>
<td align="left">Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
bounces\><bounce><email>email1@domain.com</email><status>5.1.1</status><reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com</reason><created>2009-06-10 12:40:30</created></bounce><bounce><email>email2@domain2.com</email><status>5.1.1</status><reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com</reason><created>2009-06-10 12:40:30</created></bounce></bounces>JSON Call

</h3>
{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
{"email":"email1@domain.com","status":"5.1.1","reason":"host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com","created":"2009-06-01 19:41:39"},{"email":"email2@domain2.com","status":"5.1.1","reason":"host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com","created":"2009-06-01 19:41:39"}]
{% endcodeblock %}

* * * * *


{% anchor h2 %} Delete Bounces {% endanchor %}


Since SendGrid does not re-deliver to bounced addresses, users can remove bounces from their list at any time if redelivery to a bounced address is desired.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser we are retrieving bounces from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>delete</em></td>
<td align="left">This will allow you to delete the bounces for the specified user</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Bounce email address you want to delete</td>
<td align="left">You must specify the bounced email message to remove</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=delete&email=bounce@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock %}
result\><message>Email does not exist</message></result>
{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=delete&email=bounce@example.com
{% endcodeblock %}

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
