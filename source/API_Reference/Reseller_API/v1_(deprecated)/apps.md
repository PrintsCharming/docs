---
layout: page
weight: 0
title: Apps
navigation:
   show: true
---

{% anchor h2 %} List {% endanchor %}


List all of the available apps.

Note: The *name* entry is used in all the other API calls to identify a app.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *getavailable*|Retrieve Available Apps|
|user|Yes|Customer must be registered under your account|The customer who we will update|
|method|Yes|Must be set to *apps*|Allows you to access apps functionality|

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
<filters><filter><name>twitter</name><title>Twitter</title>
      <description>This plugin allows you to send an email message to twitter</description><activated>0</activated></filter>
    ...
    </filters>
{% endcodeblock %}



### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
{"name":"twitter","title":"Twitter","description":"This plugin allows you to send an email message to twitter","activated":false}
{% endcodeblock %}

 
{% anchor h2 %} Activate App {% endanchor %}


|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *activate*|Retrieve Available Apps|
|user|Yes|Customer must be registered under your account|The customer who we will update|
|method|Yes|Must be set to *apps*|Allows you to access apps functionality|

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
<result><message>success</message></result>
{% endcodeblock %}



### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=customer@example.com
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Deactivate App {% endanchor %}


|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *deactivate*|Retrieve Available Apps|
|user|Yes|Customer must be registered under your account|The customer who we will update|
|method|Yes|Must be set to *apps*|Allows you to access apps functionality|

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
result><message>success</message></result>
{% endcodeblock %}



### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=customer@example.com
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
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
filter><field_name>field_value</field_name>
    ...
    </filter>
{% endcodeblock %}



### Response: Error



{% codeblock %}
result><message>error</message><message>... error messages ...</message></result>
{% endcodeblock %}
<h4>Return - Empty</h4>
<p>This is returned if that filter has no settings or is not enabled.</p>
{% codeblock %}
<filter></filter>
{% endcodeblock %}



### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>




#### Return - Empty

This is returned if that filter has no settings or is not enabled.



{% codeblock %}
{"settings":null}

{% endcodeblock %}
<hr/>


{% anchor h2 %}
Get Current Settings 
{% endanchor %}

<h3>XML Call</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=customer@example.com&method=app
{% endcodeblock %}



### Response: Success



{% codeblock %}
<filter><field_name>field_value</field_name>
    ...
    </filter>
{% endcodeblock %}
<h3>Response: Error</h3>
{% codeblock %}
<result><message>error</message><message>... error messages
...</message></result>
{% endcodeblock %}



#### Return - Empty

This is returned if that filter has no settings or is not enabled.



{% codeblock %}
<filter></filter>
{% endcodeblock %}
<h3>JSON Call</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=customer@example.com&method=app
{% endcodeblock %}



### Response: Success







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