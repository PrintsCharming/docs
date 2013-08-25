--- layout: page weight: 0 title: Customer Invalid Emails navigation:
show: true --- {% anchor h2 %} Retrieve Invalid Emails {% endanchor %}

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
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer we are retrieving invalid emails from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>get</em></td>
<td align="left">This will allow you to retrieve the invalid emails for the specified customer</td>
</tr>
<tr class="odd">
<td align="left">date</td>
<td align="left">No</td>
<td align="left">Must be set to 1</td>
<td align="left">Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>invalidemails</em></td>
<td align="left">Allows you to access invalid email functionality</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=customer@example.com&task=get&date=
{% endcodeblock %}

### Response

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
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=customer@example.com&task=get&date=1
{% endcodeblock %}

### Response

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
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer we are retrieving invalid emails from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>delete</em></td>
<td align="left">This will allow you to delete a invalid email for the specified customer</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Must be a invalid email</td>
<td align="left">You must specify the invalid emails to remove</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>invalidemails</em></td>
<td align="left">Allows you to access invalid emails functionality</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=customer@example.com&task=delete&email=invalidemail@example.com
{% endcodeblock %}

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
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=customer@example.com&task=delete&email=invalidemail@example.com
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

</div>
</div>

