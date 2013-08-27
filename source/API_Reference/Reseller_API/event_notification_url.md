---
layout: page
weight: 0
title: Event Notification URL
navigation:
   show: true
---

{% anchor h2 %} Retrieve {% endanchor %}


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
            <em>get</em>
         </td>
         <td>This will allow you to retrieve the event notification url for the specified customer</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The username of the customer</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>eventposturl</em>
         </td>
         <td>Allows you to access post event url functionality</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=get&amp;user=customer@example.com&amp;method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<url>http://www.SubUserPostUrlHere.com&amp;gt;</url>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=get&amp;user=customer@example.com&amp;method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "url": "http://www.SubUserPostUrlHere.com"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Update / Set URL {% endanchor %}


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
            <em>set</em>
         </td>
         <td>This will allow you to retrieve the event notification url for the specified customer</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The name of the customer</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td>The notification URL</td>
         <td>This is the new event notification URL</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>eventposturl</em>
         </td>
         <td>Allows you to access post event url functionality</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs set %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="set-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=set&amp;user=customer@example.com&amp;url=http://www.SubUserPostUrlHere.com&amp;method=eventposturl
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="set-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=set&amp;user=customer@example.com&amp;url=http://www.SubUserPostUrlHere.com&amp;method=eventposturl
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


{% anchor h2 %} Delete {% endanchor %}


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
            <em>delete</em>
         </td>
         <td>This will allow you to delete the event notification url for the specified customer</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer must be registered under your account</td>
         <td>The name of the customer</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>eventposturl</em>
         </td>
         <td>Allows you to access post event url functionality</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=delete&amp;user=customer@example.com&amp;method=eventposturl
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=delete&amp;user=customer@example.com&amp;method=eventpostur
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




</div>
</div>

