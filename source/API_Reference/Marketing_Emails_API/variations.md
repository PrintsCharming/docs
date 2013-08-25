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
<td align="left">Must be an existing Marketing Email in draft mode.</td>
<td align="left">The name of the Marketing Email you are adding Variations to.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The name of the Variation you will be adding.</td>
</tr>
<tr class="odd">
<td align="left">subject</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The subject that will be used for the Variation being created.</td>
</tr>
<tr class="even">
<td align="left">text</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The text portion of the Marketing Email Variation being added.</td>
</tr>
<tr class="odd">
<td align="left">html</td>
<td align="left">No</td>
<td align="left">If the <code>type</code> parameter is set to &quot;html&quot; this parameter is required.</td>
<td align="left">The html portion of the Marketing Email Variation being added.</td>
</tr>
<tr class="even">
<td align="left">type</td>
<td align="left">Yes</td>
<td align="left">Value must be either &quot;text&quot; or &quot;html&quot;.</td>
<td align="left">The Variation type, either plain text, or multipart-alternative text and html.</td>
</tr>
<tr class="odd">
<td align="left">identity_name</td>
<td align="left">No</td>
<td align="left">Must be an existing Marketing Email Identity</td>
<td align="left">Identity name that is needed if the Marketing Email name does not already exist. Will be used to create a parent Marketing Email.</td>
</tr>
</tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=variation_name&subject=variation_subject&html=variation_body
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
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=variation_name&subject=variation_subject&html=variation_body
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
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} edit {% endanchor %}
 Edit an existing Variation.   

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
<td align="left">Must be an existing Marketing Email with Variations added to it.</td>
<td align="left">The name of the Marketing Email you are editing Variations on.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Variation</td>
<td align="left">The name of the Variation you will be editing.</td>
</tr>
<tr class="odd">
<td align="left">newvariation</td>
<td align="left">No</td>
<td align="left">None</td>
<td align="left">The new name of the Variation.</td>
</tr>
<tr class="even">
<td align="left">subject</td>
<td align="left">No</td>
<td align="left">None</td>
<td align="left">The new subject of the Variation.</td>
</tr>
<tr class="odd">
<td align="left">text</td>
<td align="left">No</td>
<td align="left">None</td>
<td align="left">The new text portion of the Marketing Email Variation.</td>
</tr>
<tr class="even">
<td align="left">html</td>
<td align="left">No</td>
<td align="left">None</td>
<td align="left">The new html portion of the Marketing Email Variation.</td>
</tr>
<tr class="odd">
<td align="left">type</td>
<td align="left">No</td>
<td align="left">text/html</td>
<td align="left">The Variation type.</td>
</tr>
</tbody>
</table>

{% xmljsontabs edit %}

<div class="tab-content">
<div class="tab-pane active" id="edit-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/edit.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=existing_variation_name&newvariation=new_variation_name&subject=variation_subject&html=variation_body
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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/edit.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&type=html&variation=existing_variation_name&newvariation=new_variation_name&subject=variation_subject&html=variation_body
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
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} get {% endanchor %}
 Retrieve the contents of an existing Variation.   

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
<td align="left">The name of the Marketing Email with existing Variations added to it.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Variation</td>
<td align="left">The name of the Variation you would like the contents of.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=existing_variation_name
{% endcodeblock %}

### Response: Success



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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=existing_variation_name
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} cancel {% endanchor %}
 Cancels a current Variation send that is in progress.   

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
<td align="left">The name of the Marketing Email you wish to cancel, this cancels added Variations.</td>
</tr>
</tbody>
</table>

{% xmljsontabs cancel %}

<div class="tab-content">
<div class="tab-pane active" id="cancel-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/cancel.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft
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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/cancel.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}
 Delete the contents of an existing Variation.   

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
<td align="left">The name of the Marketing Email with existing Variations added to it.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">No</td>
<td align="left">Must be an existing Variation</td>
<td align="left">The name of the Variation you would like to delete.</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_delete
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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_delete
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} list {% endanchor %}
 Retrieve a list of all Variations attached to a Marketing Email.   

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
<td align="left">The marketing email for which to list variations.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">No</td>
<td align="left">Must be an existing Variation</td>
<td align="left">An optional list of names to check for.</td>
</tr>
</tbody>
</table>

{% xmljsontabs list %}

<div class="tab-content">
<div class="tab-pane active" id="list-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/list.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_find
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
<div class="tab-pane" id="list-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/list.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_to_find
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} pickwinner {% endanchor %}
 Select the Variation you would like to send.   

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
<td align="left">Select the Marketing Email you're picking the winner of.</td>
</tr>
<tr class="even">
<td align="left">variation</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Variation</td>
<td align="left">The winning Variation.</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/pickwinner.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_that_wins
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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/pickwinner.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&variation=variation_that_wins
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} schedule {% endanchor %}
 Schedule a send time and percentage for your variations.   

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
<td align="left">Select the Marketing Email you'de like to schedule Variation testing on.</td>
</tr>
<tr class="even">
<td align="left">percent</td>
<td align="left">Yes</td>
<td align="left">Must be a number 0-100</td>
<td align="left">Percentage of the total recipients that will be emailed in the test.</td>
</tr>
<tr class="odd">
<td align="left">delay</td>
<td align="left">No</td>
<td align="left">Must be numeric.</td>
<td align="left">The number of units specified by <code>delay_type</code> by which to delay the send.</td>
</tr>
<tr class="even">
<td align="left">delay_type</td>
<td align="left">No</td>
<td align="left">&quot;minutes&quot;, &quot;hours&quot;, or &quot;days&quot;</td>
<td align="left">The units used to specify the <code>delay</code></td>
</tr>
<tr class="odd">
<td align="left">date</td>
<td align="left">No</td>
<td align="left">Must be an existing Variation</td>
<td align="left">An optional list of names's to check for.</td>
</tr>
<tr class="even">
<td align="left">timezone</td>
<td align="left">No</td>
<td align="left">Must be an existing Variation</td>
<td align="left">An optional timezone of specific date (timezones are in the Olson Database name format).</td>
</tr>
</tbody>
</table>

{% xmljsontabs schedule %}

<div class="tab-content">
<div class="tab-pane active" id="schedule-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/schedule.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&percent=50
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
<div class="tab-pane" id="schedule-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/variations/schedule.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=existing_draft&percent=50
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<?xml version="1.0" encoding="ISO-8859-1" ?>
<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}

</div>
</div>

