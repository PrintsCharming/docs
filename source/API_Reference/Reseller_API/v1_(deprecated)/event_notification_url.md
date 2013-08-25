--- layout: page weight: 0 title: Event Notification URL navigation:
show: true --- {% anchor h2 %} Retrieve {% endanchor %}

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
<td align="left">This will allow you to retrieve the event notification url for the specified customer</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The username of the customer</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>eventposturl</em></td>
<td align="left">Allows you to access post event url functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=customer@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock %}
<url>http://www.SubUserPostUrlHere.com</url>JSON Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=customer@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock %}
{"url":"http:\\/\\/www.SubUserPostUrlHere.com"}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Update / Set URL {% endanchor %}

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
<td align="left">This will allow you to retrieve the event notification url for the specified customer</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The name of the customer</td>
</tr>
<tr class="odd">
<td align="left">url</td>
<td align="left">Yes</td>
<td align="left">The notification URL</td>
<td align="left">This is the new event notification URL</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>eventposturl</em></td>
<td align="left">Allows you to access post event url functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=customer@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=customer@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Delete {% endanchor %}

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
<td align="left">This will allow you to delete the event notification url for the specified customer</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The name of the customer</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>eventposturl</em></td>
<td align="left">Allows you to access post event url functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=customer@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=customer@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}
