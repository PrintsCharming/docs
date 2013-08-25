--- layout: page weight: 0 title: Customer Subuser Parse Settings
navigation: show: true --- {% anchor h2 %} Get Current Settings {%
endanchor %}

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
<td align="left">Must be set to <em>get</em></td>
<td align="left">Retrieve Parse settings</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who we will update</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=parse&task=get&method=parse&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
parse\><entry><hostname>www.example.com</hostname><url>www.mydomain.com/parse.php</url><spam_check>1</spam_check></entry></parse>Response:
Empty

</h3>
{% codeblock %} parse\></parse>JSON Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&method=parse&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
"parse":[{"hostname":"www.example.com","url":"www.mydomain.com\\/parse.php","spam_check":1}]
{% endcodeblock %}

### Response: Empty

{% codeblock %}
"parse":[]
{% endcodeblock %}

* * * * *

{% anchor h2 %} Create New Entry {% endanchor %}

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
<td align="left">Must be set to <em>set</em></td>
<td align="left">Set Parse settings</td>
</tr>
<tr class="even">
<td align="left">hostname</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">Hostname we will use with your email</td>
</tr>
<tr class="odd">
<td align="left">url</td>
<td align="left">Yes</td>
<td align="left"></td>
<td align="left">The parse destination</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who we will update</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=set&method=parse&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=set&method=parse&user=example@example.com
{% endcodeblock %}

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

* * * * *

{% anchor h2 %} Edit Entry {% endanchor %}

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
<td align="left">Must be set to <em>update</em></td>
<td align="left">Set Parse settings</td>
</tr>
<tr class="even">
<td align="left">hostname</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">Hostname entry you want to update</td>
</tr>
<tr class="odd">
<td align="left">url</td>
<td align="left">Yes</td>
<td align="left"></td>
<td align="left">The parse destination</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who we will update</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=update&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=parse&user=example@example.com
{% endcodeblock %}

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

* * * * *

{% anchor h2 %} Delete Entry {% endanchor %}

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
<td align="left">Must be set to <em>delete</em></td>
<td align="left">Set Parse settings</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The customer subuser who we will update</td>
</tr>
<tr class="odd">
<td align="left">hostname</td>
<td align="left">Yes</td>
<td align="left">Must be the hostname you wish to delete.</td>
<td align="left">The host name you will remove for your customer subuser</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&method=parse&user=example@example.com
{% endcodeblock %}

### Response: Success

{% codeblock %}
result\><message>success</message></result>
{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages
...</error>
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&method=parse&user=example@example.com
{% endcodeblock %}

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
