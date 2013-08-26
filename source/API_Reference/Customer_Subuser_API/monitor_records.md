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


{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=create&name=myMonitor&email=example@example.com&frequency=1000
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=create&name=myMonitor&email=example@example.com&frequency=1000
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
</div>

* * * * *


{% anchor h2 %} Edit Monitor Record {% endanchor %}
 Make modifications to an existing Monitor record.


{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=edit&name=myMonitor&new_name=updatedMonitor&new_email=example@example.com&new_frequency=5
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
</div>

* * * * *


{% anchor h2 %} Delete Monitor Record {% endanchor %}
 Deleting a monitor record will remove it from SendGrid's system. **Make sure no users are currently using the monitor record when removing, or removal will fail.**


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&name=recordToDelete
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&name=recordToDelete
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
</div>

* * * * *


{% anchor h2 %} List All Monitor Records {% endanchor %}
 List all available monitor records a reseller has.


{% xmljsontabs listrecords %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="listrecords-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list
{% endcodeblock %}
<h3>Response</h3>
  
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list
{% endcodeblock %}
<h3>Response</h3>
  
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


{% xmljsontabs append %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="append-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&name=myMonitor&user=example@example.com
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&name=myMonitor&user=example@example.com
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
</div>

* * * * *


{% anchor h2 %} Detach A Monitor Record From A Subuser {% endanchor %}
 Detach a subuser from a monitor record.


{% xmljsontabs detach %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="detach-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=detach&user=example@example.com
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



{% codeblock %}
https://sendgrid.com/apiv2/customer.monitor.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=detach&user=example@example.com
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
</div>

