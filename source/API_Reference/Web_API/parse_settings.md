---
layout: page
weight: 0
title: Parse Webhook Settings
navigation:
  show: true
---

{% anchor h2 %} get {% endanchor %}


Retrieve settings already configured for parsing incoming email.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
api_user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid Username

</td>
</tr>
<tr markdown="1">
<td markdown="1">
api_key

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid password

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/parse.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/api/parse.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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

{% codeblock %} <parse></parse> {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} set {% endanchor %}


Specify the hostname and url for parsing incoming emails.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
api_user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid Username

</td>
</tr>
<tr markdown="1">
<td markdown="1">
api_key

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid password

</td>
</tr>
<tr markdown="1">
<td markdown="1">
hostname

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
The hostname (domain or subdomain) for which you would like to configure a Parse Webhook callback URL.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
url

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
The callback URL to which Parse Webhook payloads will be POSTed.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
spam_check

</td>
<td markdown="1">
No

</td>
<td markdown="1">
0 or 1

</td>
<td markdown="1">
If spam check is enabled, messages that look like spam will not be POSTed.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs set %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="set-json">
### Call

{% codeblock %} https://sendgrid.com/api/parse.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1 {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="set-xml">
### Call

{% codeblock %} https://sendgrid.com/api/parse.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1 {% endcodeblock %}

### Response: Success

### 
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

* * * * *


{% anchor h2 %} Delete Entry {% endanchor %}


Delete the existing settings for parsing incoming emails.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
api_user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid Username

</td>
</tr>
<tr markdown="1">
<td markdown="1">
api_key

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
SendGrid password

</td>
</tr>
<tr markdown="1">
<td markdown="1">
hostname

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
alphanumeric

</td>
<td markdown="1">
The hostname (domain or subdomain) for which you would like to delete Parse Webhook settings.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/api/parse.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/api/parse.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com {% endcodeblock %}

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

