--- layout: page weight: 0 title: Customer Subuser Event Notification
URL navigation: show: true --- {% anchor h2 %} Retrieve {% endanchor %}

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
<td align="left">This will allow you to retrieve the event notification url for the specified customer subuser</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The username of the customer subuser</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<url>http://www.SubUserPostUrlHere.com</url>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&user=example@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "url": "http://www.SubUserPostUrlHere.com"
}
{% endcodeblock %}

</div>
</div>

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
<td align="left">This will allow you to retrieve the event notification url for the specified customer subuser</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The name of the customer subuser</td>
</tr>
<tr class="odd">
<td align="left">url</td>
<td align="left">Yes</td>
<td align="left">The notification URL</td>
<td align="left">This is the new event notification URL</td>
</tr>
</tbody>
</table>

{% xmljsontabs update %}

<div class="tab-content">
<div class="tab-pane" id="update-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="update-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&url=http://www.SubUserPostUrlHere.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

</div>
</div>

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
<td align="left">This will allow you to delete the event notification url for the specified customer subuser</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser must be registered under your account</td>
<td align="left">The name of the customer subuser</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=example@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=delete&user=example@example.com&method=eventpostur
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

</div>
</div>

