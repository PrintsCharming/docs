---
layout: page
weight: 0
title: Event Notification URL
navigation:
   show: true
---

{% anchor h2 %} Retrieve {% endanchor %}


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *get*</td>
         <td>This will allow you to retrieve the event notification url for the specified subuser</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Subuser must be registered under your account</td>
         <td>The username of the subuser</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs retrieve %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="retrieve-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.eventposturl.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=get&amp;user=example@example.com
	{% endcodeblock %}
<h3>Response</h3>
	  
{% codeblock lang:javascript %}
{
  "url": "http://www.SubUserPostUrlHere.com"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="retrieve-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.eventposturl.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=get&amp;user=example@example.co
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<url>http://www.SubUserPostUrlHere.com</url>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Update / Set URL {% endanchor %}


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *set*</td>
         <td>This will allow you to retrieve the event notification url for the specified subuser</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Subuser must be registered under your account</td>
         <td>The name of the subuser</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td>The notification URL</td>
         <td>This is the new event notification URL</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs set %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="set-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.eventposturl.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=set&amp;user=example@example.com&amp;url=http://www.SubUserPostUrlHere.co
	{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="set-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.eventposturl.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=set&amp;user=example@example.com&amp;url=http://www.SubUserPostUrlHere.co
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Delete {% endanchor %}


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>Must be set to *delete*</td>
         <td>This will allow you to delete the event notification url for the specified subuser</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Subuser must be registered under your account</td>
         <td>The name of the subuser</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.eventposturl.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=delete&amp;user=example@example.co
	{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.eventposturl.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=delete&amp;user=example@example.co
{% endcodeblock %}
<h3>Response</h3>
  
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
</div>

