---
layout: page
weight: 0
title: Customer Subuser Account Limits
navigation:
   show: true
---

Throttle your customer subuser when you need them to send only a specific amount of emails at a specified interval.

* * * * *


{% anchor h2 %} Retrieve {% endanchor %}


Retrieve account limits for a specific customer subuser. If the API call response is empty that means the customer subuser has the limits removed.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>retrieve</em></td>
<td align="left">Retrieve account limits</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who will have their account limits retrieved</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=retriev
{% endcodeblock %}

### Response: Success

{% codeblock %}
<credits><credit>0</credit><credit_remain>2000</credit_remain><last_reset>2011-02-21</last_reset></credits>Response: Error

</h3>
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>
{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=retriev
{% endcodeblock %}

### Response: Success

{% codeblock %}
{"credit":"0","credit_remain":"2000","last_reset":"2011-02-21"}
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

* * * * *


{% anchor h2 %} No Limit {% endanchor %}


Obtain a complete list of all customer subuser.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>none</em></td>
<td align="left">Remove account limits</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who will have their account limits removed</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=non
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=non
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

* * * * *


{% anchor h2 %} Recurring Reset {% endanchor %}


A recurring reset will allow you to periodically reset a subusers credits to a number you specify. This can be either daily, weekly or monthly.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>recurring</em></td>
<td align="left">The task required to set the recurring reset</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser you will be applying a recurring reset to</td>
</tr>
<tr class="odd">
<td align="left">credits</td>
<td align="left">Yes</td>
<td align="left">Must be an integer and greater than 0</td>
<td align="left">The number of credits the customer subuser will be reset to</td>
</tr>
<tr class="even">
<td align="left">period</td>
<td align="left">Yes</td>
<td align="left">Must be either daily, weekly, or monthly</td>
<td align="left">How often you want SendGrid to reset your customer subusers credits</td>
</tr>
<tr class="odd">
<td align="left">startdate</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format</td>
<td align="left">The date you want to start resetting the customer subusers credits</td>
</tr>
<tr class="even">
<td align="left">enddate</td>
<td align="left">No</td>
<td align="left">Date must be in YYYY-mm-dd format</td>
<td align="left">The date you want to stop resetting the customer subusers credits</td>
</tr>
<tr class="odd">
<td align="left">initial_credits</td>
<td align="left">No</td>
<td align="left">Must be an integer greater than 0</td>
<td align="left">The number of credits you initially want the account reset to. If this is not set, the credits will be reset using the credits parameter</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=recurring&credits=200&period=dail
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=recurring&credits=200&period=dail
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

* * * * *


{% anchor h2 %} Total Credits {% endanchor %}


Set a subusers credits to a specified amount.

<table>
<tbody>
<tr class="odd">
<td align="left">Parameter</td>
<td align="left">Required</td>
<td align="left">Requirements</td>
<td align="left">Description</td>
</tr>
<tr class="even">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>total</em></td>
<td align="left">Set the credits to the specified amount</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who will have their credits updated</td>
</tr>
<tr class="even">
<td align="left">credits</td>
<td align="left">Yes</td>
<td align="left">Must be an integer and greater than 0</td>
<td align="left">The total number of credits the customer subuser will be reset to</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=total&credits=20
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=total&credits=20
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

* * * * *


{% anchor h2 %} Increment Credits {% endanchor %}


Increment a subusers credits by a specified amount.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>increment</em></td>
<td align="left">Increment the credits by the specified amount</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who will have their credits incremented</td>
</tr>
<tr class="odd">
<td align="left">credits</td>
<td align="left">Yes</td>
<td align="left">Must be an integer and greater than 0</td>
<td align="left">The total number of credits the customer subuser will be incremented by</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=increment&credits=20
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=increment&credits=20
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

* * * * *


{% anchor h2 %} Decrement Credits {% endanchor %}


Decrement a subusers credits by a specified amount.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>increment</em></td>
<td align="left">Decrement the credits by the specified amount</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who will have their credits decremented</td>
</tr>
<tr class="odd">
<td align="left">credits</td>
<td align="left">Yes</td>
<td align="left">Must be an integer and greater than 0</td>
<td align="left">The total number of credits the customer subuser will be decremented by</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=decrement&credits=20
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=limit&user=example@example.com&task=decrement&credits=20
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
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}
