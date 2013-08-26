---
layout: page
weight: 0
title: Schedule
navigation:
  show: true
---

This endpoint allows you to add, view, or remove scheduled delivery events for Marketing Emails.


{% info %} If you wish to send a marketing email immediately, leave off the **at** and **after** parameters. {% endinfo %}
 
{% anchor h2 %} add {% endanchor %}


Schedule a delivery time for an existing Marketing Email.

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
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Marketing Email.</td>
<td align="left">Marketing Email to schedule delivery for. (If Marketing Email should be sent now, include no additional parameters.)</td>
</tr>
<tr class="even">
<td align="left">at</td>
<td align="left">No</td>
<td align="left">Date / Time must be provided in ISO 8601 format (YYYY-MM-DD HH:MM:SS+-HH:MM)</td>
<td align="left">Date / Time to schedule marketing email Delivery.</td>
</tr>
<tr class="odd">
<td align="left">after</td>
<td align="left">No</td>
<td align="left">Must be a positive integer.</td>
<td align="left">Number of minutes until delivery should occur.</td>
</tr>
</tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/schedule/add.json?name=test&at=2012-09-05_18%3A35%3A00&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/schedule/add.xml?name=test&at=2012-09-05_18%3A35%3A00&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
   <message>error: reason</message>
</result>

{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} get {% endanchor %}


Retrieve the scheduled delivery time for an existing Marketing Email.

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
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Marketing Email.</td>
<td align="left">Retrieve the delivery time scheduled for this Marketing Email.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/schedule/get.json?name=SendGrid_Test2&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "date": "2012-09-05 21:22:02"
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
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/api/newsletter/schedule/get.xml?name=SendGrid_Test2&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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

<scheduled>
   <date> 2012-09-05 21:22:02 </date>
</scheduled>

{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Cancel a scheduled send for a Marketing Email.

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
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Marketing Email</td>
<td align="left">Remove the scheduled delivery time from an existing Marketing Email.</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %} sendgrid.com/api/newsletter/schedule/delete.json?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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

{% codeblock %} sendgrid.com/api/newsletter/schedule/delete.xml?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
   <message>error: reason</message>
</result>

{% endcodeblock %}


</div>
</div>

