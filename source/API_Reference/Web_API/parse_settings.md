---
layout: page
weight: 0
title: Parse Webhook Settings
navigation:
  show: true
---

{% anchor h2 %} get {% endanchor %}


Retrieve settings already configured for parsing incoming email.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>api\_user</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid Username</td>
      </tr>
      <tr>
         <td>api\_key</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid password</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

{% codeblock lang:javascript %}
{
  "parse": [

  ]
}
{% endcodeblock %}

</div>
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

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
</div>

* * * * *


{% anchor h2 %} set {% endanchor %}


Specify the hostname and url for parsing incoming emails.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>api\_user</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid Username</td>
      </tr>
      <tr>
         <td>api\_key</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid password</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The hostname (domain or subdomain) for which you would like to configure a Parse Webhook callback URL.</td>
      </tr>
      <tr>
         <td>url</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The callback URL to which Parse Webhook payloads will be POSTed.</td>
      </tr>
      <tr>
         <td>spam\_check</td>
         <td>No</td>
         <td>0 or 1</td>
         <td>If spam check is enabled, messages that look like spam will not be POSTed.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs set %}

<div class="tab-content">
<div class="tab-pane active" id="set-json">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1
{% endcodeblock %}

### Response: Success

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
<div class="tab-pane" id="set-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1
{% endcodeblock %}

### Response: Success

### {% codeblock lang:xml %}
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
   @nodes
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Delete Entry {% endanchor %}


Delete the existing settings for parsing incoming emails.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>api\_user</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid Username</td>
      </tr>
      <tr>
         <td>api\_key</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>SendGrid password</td>
      </tr>
      <tr>
         <td>hostname</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The hostname (domain or subdomain) for which you would like to delete Parse Webhook settings.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com
{% endcodeblock %}

### Response: Success

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
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/parse.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com
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
   @nodes
</result>

{% endcodeblock %}

</div>
</div>

