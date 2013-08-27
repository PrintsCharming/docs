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


{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=getavailable&amp;method=apps&amp;user=example@example.com
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




</div>
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=getavailable&amp;method=apps&amp;user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "name": "twitter",
  "title": "Twitter",
  "description": "This plugin allows you to send an email message to twitter",
  "activated": false
}
{% endcodeblock %}




</div>
</div>

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


{% xmljsontabs activate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="activate-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=activate&amp;user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="activate-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=activate&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
</div>

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


{% xmljsontabs deactivate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="deactivate-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=deactivate&amp;user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="deactivate-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=deactivate&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Customize App {% endanchor %}


These API calls require that settings are passed using POST.

{% xmljsontabs customize %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="customize-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=setup&amp;user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}  <filter><field_name>field_value</field_name>
    ...
  </filter>
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




#### Return - Empty

This is returned if that filter has no settings or is not enabled.



{% codeblock %}
<filter></filter>
{% endcodeblock %}
</div>
<div class="tab-pane active" id="customize-json">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;method=apps&amp;task=setup&amp;user=example@example.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "message": "success",
  "settings": [
    {
      "field_name": "field_value"
    }
  ]
}
{% endcodeblock %}




#### Return - Empty

This is returned if that filter has no settings or is not enabled.



{% codeblock %}
"settings":null}
{% endcodeblock %}
</div>
</div>
<hr/>


{% anchor h2 %}
Get Current Settings 
{% endanchor %}


{% xmljsontabs settings %}
<div class="tab-content">
<div class="tab-pane" id="settings-xml">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;task=getsettings&amp;user=example@example.com&amp;method=app
{% endcodeblock %}



### Response: Success



{% codeblock %}  <filter><field_name>field_value</field_name>
    ...
  </filter>
{% endcodeblock %}
<h3>Response: Error</h3>

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




#### Return - Empty

This is returned if that filter has no settings or is not enabled.



{% codeblock %}
<filter></filter>
{% endcodeblock %}
</div>
<div class="tab-pane active" id="settings-json">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;name=twitter&amp;task=getsettings&amp;user=example@example.com&amp;method=app
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "message": "success",
  "settings": [
    {
      "field_name": "field_value"
    }
  ]
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




#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} "settings":null {% endcodeblock %}

</div>
</div>

