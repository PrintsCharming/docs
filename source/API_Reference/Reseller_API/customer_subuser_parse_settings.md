---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---

{% anchor h2 %} Get Current Settings {% endanchor %}


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
         <td>Retrieve Parse settings</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;method=parse&amp;task=get&amp;method=parse&amp;user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<parse>
   <entry>
      <hostname>www.example.com</hostname>
      <url>www.mydomain.com/parse.php</url>
      <spam_check>1</spam_check>
   </entry>
</parse>

{% endcodeblock %}




### Response: Empty



{% codeblock %}
<parse></parse>
{% endcodeblock %}
</div>
<div class="tab-pane active" id="get-json">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;task=get&amp;method=parse&amp;user=example@example.com
{% endcodeblock %}



### Response: Success




{% codeblock lang:javascript %}
{
  "parse": [
    {
      "hostname": "www.example.com",
      "url": "www.mydomain.com/parse.php",
      "spam_check": 1
    }
  ]
}
{% endcodeblock %}




### Response: Empty



{% codeblock %}
"parse":[]
{% endcodeblock %}
</div>
</div>
<hr/>


{% anchor h2 %}
Create New Entry 
{% endanchor %}

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Required</th>
      <th>Requirements</th>
      <th>Description</th>
   </tr>
   <tr>
      <td>task</td>
      <td>Yes</td>
      <td>
         Must be set to
         <em>set</em>
      </td>
      <td>Set Parse settings</td>
   </tr>
   <tr>
      <td>hostname</td>
      <td>Yes</td>
      <td>No more than 255 characters</td>
      <td>Hostname we will use with your email</td>
   </tr>
   <tr>
      <td>url</td>
      <td>Yes</td>
      <td/>
      <td>The parse destination</td>
   </tr>
   <tr>
      <td>user</td>
      <td>Yes</td>
      <td>Customer subuser must be registered under		your account</td>
      <td>The customer subuser who we will update</td>
   </tr>
</table>

{% xmljsontabs create %}
<div class="tab-content">
<div class="tab-pane" id="create-xml">
<h3>Call</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;url=www.mydomain.com/parse.php&amp;spam_check=1&amp;method=parse&amp;task=set&amp;method=parse&amp;user=example@example.com
{% endcodeblock %}



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



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;url=www.mydomain.com/parse.php&amp;spam_check=1&amp;method=parse&amp;task=set&amp;method=parse&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

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


{% anchor h2 %} Edit Entry {% endanchor %}


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
            <em>update</em>
         </td>
         <td>Set Parse settings</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>No more than 255 characters</td>
         <td>Hostname entry you want to update</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td/>
         <td>The parse destination</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;url=www.mydomain.com/parse.php&amp;spam_check=1&amp;method=parse&amp;task=update&amp;user=example@example.com
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
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;url=www.mydomain.com/parse.php&amp;spam_check=1&amp;method=parse&amp;task=parse&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

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


{% anchor h2 %} Delete Entry {% endanchor %}


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
         <td>Set Parse settings</td>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser must be registered under your account</td>
         <td>The customer subuser who we will update</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>Must be the hostname you wish to delete.</td>
         <td>The host name you will remove for your customer subuser</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;task=delete&amp;method=parse&amp;user=example@example.com
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
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;hostname=www.example.com&amp;task=delete&amp;method=parse&amp;user=example@example.com
{% endcodeblock %}
<h3>Response</h3>

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

