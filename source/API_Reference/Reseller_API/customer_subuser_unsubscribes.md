--- layout: page weight: 0 title: Customer Subuser Unsubscribes
navigation: show: true --- {% anchor h2 %} Retrieve Unsubscribes {%
endanchor %}

Note that you can use *either* the days parameter *or* the start\_date
and end\_date parameter.

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
<td align="left">The customer subuser we are retrieving unsubscribes from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>get</em></td>
<td align="left">This will allow you to retrieve the unsubscribes for the specified customer subuser</td>
</tr>
<tr class="odd">
<td align="left">date</td>
<td align="left">No</td>
<td align="left">Must be set to 1</td>
<td align="left">Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=get&date=
{% endcodeblock %}

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
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=get&date=
{% endcodeblock %}

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

Since SendGrid does not deliver to unsubscribe addresses, users can
remove unsubscribes from their list at any time if re-delivery to an
unsubscribed address is desired.

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
<td align="left">The customer subuser we are retrieving unsubscribes from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>delete</em></td>
<td align="left">This will allow you to delete an unsubscribe record for the specified customer subuser</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Must be an unsubscribe record</td>
<td align="left">You must specify the unsubscribe record to remove</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=delete&email=unsubscribe@sample.com
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
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=delete&email=unsubscribe@sample.com
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

* * * * *

{% anchor h2 %} Add Unsubscribes {% endanchor %}

Add unsubscribe email records to their account if they need to stop
sending email messages to a specific recipient.

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
<td align="left">The customer subuser we are retrieving unsubscribes from</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>add</em></td>
<td align="left">This will allow you to add an unsubscribe record for the specified customer subuser</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Must be an unsubscribe record</td>
<td align="left">You must specify the unsubscribe record to add</td>
</tr>
</tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=add&email=unsubscribe@sample.com
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
   <message>Email already exists</message>
</result>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=unsubscribes&user=example@example.com&task=add&email=unsubscribe@sample.com
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
  "message": "Email already exists"
}
{% endcodeblock %}

</div>
</div>

