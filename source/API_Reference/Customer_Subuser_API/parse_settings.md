---
layout: page
weight: 0
title: Parse Settings
navigation:
   show: true
---

{% anchor h2 %} Get Current Settings {% endanchor %}


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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *get*

</td>
<td markdown="1">
Retrieve Parse settings

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who we will update

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com {% endcodeblock %}

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


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<parse/>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com {% endcodeblock %}

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
</div>

* * * * *


{% anchor h2 %} Create New Entry {% endanchor %}


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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *set*

</td>
<td markdown="1">
Set Parse settings

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
No more than 255 characters

</td>
<td markdown="1">
Hostname we will use with your email

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
</td>
<td markdown="1">
The parse destination

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who we will update

</td>
</tr>
</tbody>
</table>
{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&task=set&user=example@example.com {% endcodeblock %}

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

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&task=set&user=example@example.com {% endcodeblock %}

### Response


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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *update*

</td>
<td markdown="1">
Set Parse settings

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
No more than 255 characters

</td>
<td markdown="1">
Hostname entry you want to update

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
</td>
<td markdown="1">
The parse destination

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who we will update

</td>
</tr>
</tbody>
</table>
{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="edit-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&task=update&user=example@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="edit-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&task=parse&user=example@example.com {% endcodeblock %}

### Response


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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *delete*

</td>
<td markdown="1">
Set Parse settings

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The subuser who we will update

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
Must be the hostname you wish to delete.

</td>
<td markdown="1">
The host name you will remove for your subuser

</td>
</tr>
</tbody>
</table>
{% xmljsontabs data %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="data-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&user=example@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="data-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.parse.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&user=example@example.com {% endcodeblock %}

### Response


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

