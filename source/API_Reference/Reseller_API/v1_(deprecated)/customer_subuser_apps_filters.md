---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---

{% anchor h2 %} List {% endanchor %}


List all of the available apps.

Note: The *name* entry is used in all the other API calls to identify a app.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>getavailable</em>
         </td>
         <td>Retrieve Available Apps</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filters>
   <filter>
      <name>twitter</name>
      <title>Twitter</title>
      <description>This plugin allows you to send an email message to twitter</description>
      <activated>0</activated>
   </filter>
   ...
</filters>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>




* * * * *


{% anchor h2 %} Activate App {% endanchor %}


<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>activate</em>
         </td>
         <td>Retrieve Available Apps</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Deactivate App {% endanchor %}


<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>deactivate</em>
         </td>
         <td>Retrieve Available Apps</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Customize App {% endanchor %}


These API calls require that settings are passed using POST.

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field_value</field_name>
   ...
</filter>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages ...</message>
</result>

{% endcodeblock %}




#### Return - Empty

This is returned if that filter has no settings or is not enabled.




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>




#### Return - Empty

This is returned if that filter has no settings or is not enabled.




{% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Get Current Settings {% endanchor %}


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com&method=app
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field_value</field_name>
   ...
</filter>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages ...</message>
</result>

{% endcodeblock %}




#### Return - Empty

This is returned if that filter has no settings or is not enabled.




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com&method=app
{% endcodeblock %}
<h3>Response: Success</h3>




### Response: Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} {"settings":null} {% endcodeblock %}
