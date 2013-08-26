---
layout: page
weight: 0
title: Monitor Records
navigation:
   show: true
---

Receive a sample of an outgoing message by a specific subuser.

The first step is to create a Monitor Record. Once the monitor record has been created, a reseller can append a monitor record to a subuser. Multiple subuser can be appended to a single monitor record.


{% anchor h2 %} Create Monitor Record {% endanchor %}
 Obtain a complete list of all subuser.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *create*

</td>
<td markdown="1">
Create a monitor record

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Name must be unique. Can't be more than 255 characters

</td>
<td markdown="1">
The unique name to identify this monitor record

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The email destination to send the email sample to

</td>
</tr>
<tr markdown="1">
<td markdown="1">
frequency

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The frequency of emails to be sent out

</td>
</tr>
</tbody>
</table>
{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=create&name=myMonitor&email=example@example.com&frequency=1000 {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="create-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=create&name=myMonitor&email=example@example.com&frequency=1000 {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} Edit Monitor Record {% endanchor %}
 Make modifications to an existing Monitor record.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *edit*

</td>
<td markdown="1">
The task required to edit a monitor

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
The name of the previous monitor record

</td>
<td markdown="1">
The monitor record we are going to edit

</td>
</tr>
<tr markdown="1">
<td markdown="1">
new_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
New name must be unique and can't be more than 255 characters

</td>
<td markdown="1">
The new monitor record name

</td>
</tr>
<tr markdown="1">
<td markdown="1">
new_email

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The new email destination to send the email sample to

</td>
</tr>
<tr markdown="1">
<td markdown="1">
new_frequency

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be an integer and greater than 0

</td>
<td markdown="1">
The new frequency of emails to be sent out

</td>
</tr>
</tbody>
</table>
{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="edit-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5 {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="edit-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5 {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} Delete Monitor Record {% endanchor %}
 Deleting a monitor record will remove it from SendGrid's system. **Make sure no users are currently using the monitor record when removing, or removal will fail.**

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *delete*

</td>
<td markdown="1">
The task required to remove a monitor

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a monitor record to remove

</td>
<td markdown="1">
The unique name to identify this monitor record

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&name=recordToDelete {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&name=recordToDelete {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} List All Monitor Records {% endanchor %}
 List all available monitor records a reseller has.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *list*

</td>
<td markdown="1">
The task required to list all monitor records

</td>
</tr>
</tbody>
</table>
{% xmljsontabs listrecords %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="listrecords-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<monitors>
   <monitor>
      <name>sampleNameA</name>
      <email>example@example.com</email>
      <frequency>1000</frequency>
      <users/>
   </monitor>
   <monitor>
      <name>sampleNameB</name>
      <email>example@example.com</email>
      <frequency>10000</frequency>
      <users>
         <user>user1@example.com</user>
         <user>user2@example.com</user>
      </users>
   </monitor>
</monitors>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="listrecords-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
[
  {
    "name": "sampleNameA",
    "email": "example@example.com",
    "frequency": "1000",
    "users": [

    ]
  },
  {
    "name": "sampleNameB",
    "email": "example@example.com",
    "frequency": "10000",
    "users": [
      "user1@example.com",
      "user2@example.com"
    ]
  }
]
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Append A Subuser To A Monitor Record {% endanchor %}
 Append a monitor record to a existing record onto a subuser.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *append*

</td>
<td markdown="1">
The task required to append a monitor record to a subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The user we will append a monitor record to

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Must be a valid monitor record

</td>
<td markdown="1">
The name of the monitor record we will be appending

</td>
</tr>
</tbody>
</table>
{% xmljsontabs append %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="append-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&name=myMonitor&user=example@example.com {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="append-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&name=myMonitor&user=example@example.com {% endcodeblock %}

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


</div>
</div>

* * * * *


{% anchor h2 %} Detach A Monitor Record From A Subuser {% endanchor %}
 Detach a subuser from a monitor record.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *detach*

</td>
<td markdown="1">
The task required to detach a monitor record to a subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser we will detach the monitor record from

</td>
</tr>
</tbody>
</table>
{% xmljsontabs detach %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="detach-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=detach&user=example@example.com {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="detach-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=detach&user=example@example.com {% endcodeblock %}

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


</div>
</div>

