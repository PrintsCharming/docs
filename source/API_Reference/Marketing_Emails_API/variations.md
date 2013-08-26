---
layout: page
weight: 0
title: Variations (A/B Testing)
navigation:
  show: true
---

This module allows you to add new Variations to your drafted Marketing Emails. These Variations can be used in A/B testing (also sometimes called split testing).

* * * * *


{% anchor h2 %} add {% endanchor %}


Create a new Variation.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email in draft mode.|The name of the Marketing Email you are adding Variations to.|
|variation|Yes|None|The name of the Variation you will be adding.|
|subject|Yes|None|The subject that will be used for the Variation being created.|
|text|Yes|None|The text portion of the Marketing Email Variation being added.|
|html|No|If the `type` parameter is set to "html" this parameter is required.|The html portion of the Marketing Email Variation being added.|
|type|Yes|Value must be either "text" or "html".|The Variation type, either plain text, or multipart-alternative text and html.|
|identity\_name|No|Must be an existing Marketing Email Identity|Identity name that is needed if the Marketing Email name does not already exist. Will be used to create a parent Marketing Email.|

{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=variation_name&subject=variation_subject&html=variation_body
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
https://sendgrid.com/api/newsletter/variations/add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=variation_name&subject=variation_subject&html=variation_body
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


{% anchor h2 %} edit {% endanchor %}
 Edit an existing Variation.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email with Variations added to it.|The name of the Marketing Email you are editing Variations on.|
|variation|Yes|Must be an existing Variation|The name of the Variation you will be editing.|
|newvariation|No|None|The new name of the Variation.|
|subject|No|None|The new subject of the Variation.|
|text|No|None|The new text portion of the Marketing Email Variation.|
|html|No|None|The new html portion of the Marketing Email Variation.|
|type|No|text/html|The Variation type.|

{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="edit-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/edit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=existing_variation_name&newvariation=new_variation_name&subject=variation_subject&html=variation_body
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
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/edit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=existing_variation_name&newvariation=new_variation_name&subject=variation_subject&html=variation_body
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
 Retrieve the contents of an existing Variation.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|The name of the Marketing Email with existing Variations added to it.|
|variation|Yes|Must be an existing Variation|The name of the Variation you would like the contents of.|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=existing_variation_name
{% endcodeblock %}
<h3>Response: Success</h3>
<h3>Response: Error</h3>

{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=existing_variation_name
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} cancel {% endanchor %}
 Cancels a current Variation send that is in progress.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|The name of the Marketing Email you wish to cancel, this cancels added Variations.|

{% xmljsontabs cancel %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="cancel-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/cancel.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft
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
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/cancel.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}
 Delete the contents of an existing Variation.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|The name of the Marketing Email with existing Variations added to it.|
|variation|No|Must be an existing Variation|The name of the Variation you would like to delete.|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_delete
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
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_delete
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} list {% endanchor %}
 Retrieve a list of all Variations attached to a Marketing Email.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|The marketing email for which to list variations.|
|variation|No|Must be an existing Variation|An optional list of names to check for.|

{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/list.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_find
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
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/list.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_find
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} pickwinner {% endanchor %}
 Select the Variation you would like to send.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|Select the Marketing Email you're picking the winner of.|
|variation|Yes|Must be an existing Variation|The winning Variation.|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/pickwinner.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_that_wins
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
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/pickwinner.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_that_wins
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} schedule {% endanchor %}
 Schedule a send time and percentage for your variations.   

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|Select the Marketing Email you'de like to schedule Variation testing on.|
|percent|Yes|Must be a number 0-100|Percentage of the total recipients that will be emailed in the test.|
|delay|No|Must be numeric.|The number of units specified by `delay_type` by which to delay the send.|
|delay\_type|No|"minutes", "hours", or "days"|The units used to specify the `delay`|
|date|No|Must be an existing Variation|An optional list of names's to check for.|
|timezone|No|Must be an existing Variation|An optional timezone of specific date (timezones are in the Olson Database name format).|

{% xmljsontabs schedule %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="schedule-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/schedule.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&percent=50
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
<div markdown="1" class="tab-pane" id="schedule-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/variations/schedule.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&percent=50
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1"?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

