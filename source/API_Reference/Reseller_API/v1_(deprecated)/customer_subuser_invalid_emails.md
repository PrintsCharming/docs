--- layout: page weight: 0 title: Customer Subuser Invalid Emails
navigation: show: true --- {% anchor h2 %} Retrieve Invalid Emails {%
endanchor %}

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
<td align="left">The customer subuser we are retrieving invalid emails from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>get</em></td>
<td align="left">This will allow you to retrieve the invalid emails for the specified customer subuser</td>
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
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
invalidemails\><invalidemail><email>isaac@hotmail.comm</email><reason>Mail
domain mentioned in email address is unknown</reason><created>2009-06-10
12:40:30</created></invalidemail><invalidemail><email>isaac@hotmail</email><reason>Bad
Syntax</reason><created>2009-06-10
12:40:30</created></invalidemail><invalidemail><email>isaac@example.com</email><reason>Known
bad domain</reason><created>2009-06-10
12:40:30</created></invalidemail></invalidemails>JSON Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=get&date=
{% endcodeblock %}

### Response

{% codeblock %}
{"email":"isaac@hotmail.comm","reason":"Mail domain
mentioned in email address is unknown","created":"2009-06-01
19:41:39"},{"email":"isaac@hotmail","reason":"Bad
Syntax","created":"2009-06-01
19:41:39"},{"email":"isaac@example.com","reason":"Known bad
domain","created":"2009-06-01 19:41:39"}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Delete Invalid Emails {% endanchor %}

Since SendGrid does not deliver to invalid emails, users can remove
invalid emails from their list at any time if re-delivery to a spam
reported address is desired.

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
<td align="left">The customer subuser we are retrieving invalid emails from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>delete</em></td>
<td align="left">This will allow you to delete a invalid email for the specified customer subuser</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Must be a invalid email</td>
<td align="left">You must specify the invalid emails to remove</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=delete&email=invalidemail@example.com
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
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=delete&email=invalidemail@example.com
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
