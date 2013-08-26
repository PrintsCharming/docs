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

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email.|Marketing Email to schedule delivery for. (If Marketing Email should be sent now, include no additional parameters.)|
|at|No|Date / Time must be provided in ISO 8601 format (YYYY-MM-DD HH:MM:SS+-HH:MM)|Date / Time to schedule marketing email Delivery.|
|after|No|Must be a positive integer.|Number of minutes until delivery should occur.|

{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/schedule/add.json?name=test&at=2012-09-05_18%3A35%3A00&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

          <h3>Response: Success</h3>

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
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/schedule/add.xml?name=test&at=2012-09-05_18%3A35%3A00&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} get {% endanchor %}


Retrieve the scheduled delivery time for an existing Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email.|Retrieve the delivery time scheduled for this Marketing Email.|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/schedule/get.json?name=SendGrid_Test2&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

          <h3>Response: Success</h3>

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
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/schedule/get.xml?name=SendGrid_Test2&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

<scheduled>
   <date>
    2012-09-05 21:22:02
  </date>
</scheduled>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Cancel a scheduled send for a Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|Remove the scheduled delivery time from an existing Marketing Email.|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
sendgrid.com/api/newsletter/schedule/delete.json?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

          <h3>Response: Success</h3>

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



{% codeblock %}
sendgrid.com/api/newsletter/schedule/delete.xml?name=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

