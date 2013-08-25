--- layout: page weight: 0 title: Apps navigation: show: true --- {%
anchor h2 %} List {% endanchor %} List all of the available apps. Note:
The *name* entry is used in all the other API calls to identify a app.

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
<td align="left">Must be set to <em>getavailable</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser who we will update</td>
</tr>
</tbody>
</table>

{% xmljsontabs list %}

<div class="tab-content">
<div class="tab-pane active" id="list-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&user=example@example.com
{% endcodeblock %}

### Response: Success



</div>
<div class="tab-pane" id="list-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filters>
   <filter>
      <name>twitter</name>
      <title>
Twitter

</title>
      <description>This plugin allows you to send an email message to
twitter</description>
      <activated>0</activated>
   </filter>
</filters>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} Activate App {% endanchor %}

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
<td align="left">Must be set to <em>activate</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser who we will update</td>
</tr>
</tbody>
</table>

{% xmljsontabs activate %}

<div class="tab-content">
<div class="tab-pane active" id="activate-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=activate&user=example@example.com
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="activate-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=activate&user=example@example.com
{% endcodeblock %}

### Response: Success

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
<td align="left">Must be set to <em>deactivate</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
<td align="left">The subuser who we will update</td>
</tr>
</tbody>
</table>

{% xmljsontabs deactivate %}

<div class="tab-content">
<div class="tab-pane active" id="deactivate-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=deactivate&user=example@example.com
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="deactivate-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=deactivate&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} Customize App {% endanchor %} These API calls require
that settings are passed using POST. {% xmljsontabs customize %}

<div class="tab-content">
<div class="tab-pane active" id="customize-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=setup&user=example@example.com
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

</div>
<div class="tab-pane" id="customize-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=setup&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field\_value</field_name>
   ...
</filter>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages
...</message>
</result>

{% endcodeblock %}

#### Return - Empty

This is returned if that filter has no settings or is not enabled. {% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} Get Current Settings {% endanchor %} {% xmljsontabs
settings %}

<div class="tab-content">
<div class="tab-pane active" id="settings-json">
### Call

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

This is returned if that filter has no settings or is not enabled. {% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="settings-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.apps.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field\_value</field_name>
   ...
</filter>

{% endcodeblock %}

### Response: Error

{% codeblock %}
<result><message>error</message><message>... error
messages ...</message></result>
{% endcodeblock %}

#### Return - Empty

This is returned if that filter has no settings or is not enabled. {% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}

</div>
</div>

