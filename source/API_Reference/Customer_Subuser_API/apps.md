---
layout: page
weight: 0
title: Apps
navigation:
   show: true
---

{% anchor h2 %} List {% endanchor %}
 List all of the available apps. Note: The *name* entry is used in all the other API calls to identify a app.

||
|Parameter|Required|Requirements|Description|
|task|Yes|Must be set to *getavailable*|Retrieve Available Apps|
|user|Yes|Subuser must be registered under your account|The subuser who we will update|

{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&user=example@example.com
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
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&user=example@example.com
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
</filters>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Activate App {% endanchor %}


||
|Parameter|Required|Requirements|Description|
|task|Yes|Must be set to *activate*|Retrieve Available Apps|
|user|Yes|Subuser must be registered under your account|The subuser who we will update|

{% xmljsontabs activate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="activate-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=activate&user=example@example.com
	{% endcodeblock %}
	<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="activate-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=activate&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Deactivate App {% endanchor %}


||
|Parameter|Required|Requirements|Description|
|task|Yes|Must be set to *deactivate*|Retrieve Available Apps|
|user|Yes|Subuser must be registered under your account|The subuser who we will update|

{% xmljsontabs deactivate %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="deactivate-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=deactivate&user=example@example.com
	{% endcodeblock %}
	<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="deactivate-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=deactivate&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Customize App {% endanchor %}
 These API calls require that settings are passed using POST. {% xmljsontabs customize %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="customize-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=setup&user=example@example.com
	{% endcodeblock %}
	<h3>Response: Success</h3>
	  
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


{% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}

	</div>
  <div class="tab-pane" id="customize-xml">
   <h3>Call</h3>
  {% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=setup&user=example@example.com
{% endcodeblock %}



### Response: Success




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

    </div>

</div>
  <hr/>
  
{% anchor h2 %}
Get Current Settings 
{% endanchor %}

  
{% xmljsontabs settings %}

<div class="tab-content">
	  <div class="tab-pane active" id="settings-json">
	   <h3>Call</h3>
	{% codeblock %}
	https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com
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


{% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="settings-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com
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



{% codeblock %}    <result><message>error</message><message>... error messages ...</message></result>
{% endcodeblock %}
  <h4>Return - Empty</h4>
  This is returned if that filter has no settings or is not enabled.
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}




</div>
</div>
