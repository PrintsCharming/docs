--- layout: page weight: 0 title: Monitor Records navigation: show: true
---

Receive a sample of an outgoing message by a specific customer.

The first step is to create a Monitor Record. Once the monitor record
has been created, a reseller can append a monitor record to a customer.
Multiple customer can be appended to a single monitor record.

* * * * *

{% anchor h2 %} Create Monitor Record {% endanchor %}

Obtain a complete list of all customer.

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
<td align="left">Must be set to <em>create</em></td>
<td align="left">Create a monitor record</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">Name must be unique. Can't be more than 255 characters</td>
<td align="left">The unique name to identify this monitor record</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">Yes</td>
<td align="left">Must be in email format</td>
<td align="left">The email destination to send the email sample to</td>
</tr>
<tr class="even">
<td align="left">frequency</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The frequency of emails to be sent out</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=create&name=myMonitor&email=example@example.com&frequency=1000
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
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=create&name=myMonitor&email=example@example.com&frequency=1000
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

{% anchor h2 %} Edit Monitor Record {% endanchor %}

Make modifications to an existing Monitor record.

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
<td align="left">Must be set to <em>edit</em></td>
<td align="left">The task required to edit a monitor</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">The name of the previous monitor record</td>
<td align="left">The monitor record we are going to edit</td>
</tr>
<tr class="odd">
<td align="left">new_name</td>
<td align="left">No</td>
<td align="left">New name must be unique and can't be more than 255 characters</td>
<td align="left">The new monitor record name</td>
</tr>
<tr class="even">
<td align="left">new_email</td>
<td align="left">No</td>
<td align="left">Must be in email format</td>
<td align="left">The new email destination to send the email sample to</td>
</tr>
<tr class="odd">
<td align="left">new_frequency</td>
<td align="left">No</td>
<td align="left">Must be an integer and greater than 0</td>
<td align="left">The new frequency of emails to be sent out</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5
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
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5
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

{% anchor h2 %} Delete Monitor Record {% endanchor %}

Deleting a monitor record will remove it from SendGrid's system. **Make
sure no users are currently using the monitor record when removing, or
removal will fail.**

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
<td align="left">Must be set to <em>delete</em></td>
<td align="left">The task required to remove a monitor</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">Must be a monitor record to remove</td>
<td align="left">The unique name to identify this monitor record</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=delete&name=recordToDelet
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
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=delete&name=recordToDelet
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

{% anchor h2 %} List All Monitor Records {% endanchor %}

List all available monitor records a reseller has.

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
<td align="left">Must be set to <em>list</em></td>
<td align="left">The task required to list all monitor records</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=lis
{% endcodeblock %}

### Response

{% codeblock %}
monitors\><monitor><name>sampleNameA</name><email>example@example.com</email><frequency>1000</frequency><users></users></monitor><monitor><name>sampleNameB</name><email>example@example.com</email><frequency>10000</frequency><users><user>user1@example.com</user><user>user2@example.com</user></users></monitor></monitors>JSON
Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=lis
{% endcodeblock %}

### Response

{% codeblock %}
{"name":"sampleNameA","email":"example@example.com","frequency":"1000","users":[]},{"name":"sampleNameB","email":"example@example.com","frequency":"10000","users":["user1@example.com","user2@example.com"]}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Append A Customer To A Monitor Record {% endanchor %}

Append a monitor record to a existing record onto a customer.

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
<td align="left">Must be set to <em>append</em></td>
<td align="left">The task required to append a monitor record to a customer</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The user we will append a monitor record to</td>
</tr>
<tr class="odd">
<td align="left">name</td>
<td align="left">No</td>
<td align="left">Must be a valid monitor record</td>
<td align="left">The name of the monitor record we will be appending</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=append&name=myMonitor&user=customer@example.com
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
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=append&name=myMonitor&user=customer@example.com
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

{% anchor h2 %} Detach A Monitor Record From A Customer {% endanchor %}

Detach a customer from a monitor record.

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
<td align="left">Must be set to <em>detach</em></td>
<td align="left">The task required to detach a monitor record to a customer</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer we will detach the monitor record from</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>monitor</em></td>
<td align="left">Allows you to access monitor functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=detach&user=customer@example.com
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
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=monitor&task=detach&user=customer@example.com
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
