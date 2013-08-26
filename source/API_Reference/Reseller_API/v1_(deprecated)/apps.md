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
<td align="left">Must be set to <em>getavailable</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer who we will update</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>apps</em></td>
<td align="left">Allows you to access apps functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=customer@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} <filters><filter><name>twitter</name>

<title>
Twitter

</title>
<description>This plugin allows you to send an email message to twitter</description><activated>0</activated></filter> ... </filters> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=customer@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} {"name":"twitter","title":"Twitter","description":"This plugin allows you to send an email message to twitter","activated":false} {% endcodeblock %} 
{% anchor h2 %} Activate App {% endanchor %}


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
<td align="left">Must be set to <em>activate</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer who we will update</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>apps</em></td>
<td align="left">Allows you to access apps functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=customer@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} <result><message>success</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=customer@example.com {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Deactivate App {% endanchor %}


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
<td align="left">Must be set to <em>deactivate</em></td>
<td align="left">Retrieve Available Apps</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The customer who we will update</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>apps</em></td>
<td align="left">Allows you to access apps functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=customer@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} result\><message>success</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=customer@example.com {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Customize App {% endanchor %}


These API calls require that settings are passed using POST.

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=customer@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} filter\><field_name>field_value</field_name> ... </filter> {% endcodeblock %}

### Response: Error

{% codeblock %} result\><message>error</message><message>... error messages ...</message></result> {% endcodeblock %}

#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} <filter></filter> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=customer@example.com {% endcodeblock %}

### Response: Success



#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} {"settings":null} {% endcodeblock %}

* * * * *


{% anchor h2 %} Get Current Settings {% endanchor %}


### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=customer@example.com&method=app {% endcodeblock %}

### Response: Success

{% codeblock %} <filter><field_name>field_value</field_name> ... </filter> {% endcodeblock %}

### Response: Error

{% codeblock %} <result><message>error</message><message>... error messages ...</message></result> {% endcodeblock %}

#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} <filter></filter> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=customer@example.com&method=app {% endcodeblock %}

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
