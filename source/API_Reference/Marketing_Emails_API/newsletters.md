---
layout: page
weight: 0
title: Marketing Emails
navigation:
  show: true
---

This endpoint allows you to add, view, or remove marketing emails.


{% anchor h2 %} add {% endanchor %}


Create a new Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|identity|Yes|Must be an existing Identity|The Identity that will be used for the Marketing Email being created.|
|name|Yes|None|The name that will be used for the Marketing Email being created.|
|subject|Yes|None|The subject that will be used for the Marketing Email being created.|
|text|Yes|None|The text portion of the Marketing Email being created.|
|html|Yes|None|The html portion of the Marketing Email being created.|

{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/add.json?identity=Sender_Address&name=SendGrid_Test&subject=testsubject&text=testtextbody&html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane" id="create-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/add.xml?identity=Sender_Address&name=SendGrid_Test&subject=testsubject&text=testtextbody&html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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


Edit an existing Marketing Email.

<table markdown="1" class="table table-bordered table-striped">
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
<td markdown="1">
name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an existing Identity

</td>
<td markdown="1">
The name of the Marketing Email being updated.

</td>
</tr>
<tr markdown="1">
<tr markdown="1">
<td markdown="1">
newname

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The new name for the Marketing Email being edited.

</td>
</tr>
<tr markdown="1">
<tr markdown="1">
<td markdown="1">
identity

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be an existing Identity

</td>
<td markdown="1">
The new Identity for the Marketing Email being edited.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
subject

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The new subject that will be used for the Marketing Email being edited.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The new text portion of the Marketing Email being edited.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
html

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
The new html portion of the Marketing Email being edited.

</td>
</tr>
</table>
{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="edit-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/edit.json?identity=Sender_Address&name=SendGrid_Edit_Test&newname=new_name_test&subject=test_subject&text=test_text&html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/edit.xml?identity=Sender_Address&name=SendGrid_Edit_Test&newname=new_name_test&subject=test_subject&text=test_text&html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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


Retrieve the contents of an existing Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|Retrieve the content of an existing Marketing Email.|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/get.json?name=SendGrid_Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "can_edit": true,
  "name": "SendGrid NL Test",
  "text": null,
  "newsletter_id": 38074,
  "total_recipients": 1,
  "html": null,
  "type": "html",
  "date_schedule": null,
  "identity": "d22de3a53fac1abef944c80c19032c2c",
  "subject": null
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
https://sendgrid.com/api/newsletter/get.xml?name=SendGrid_Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<newsletter>
   <can_edit>True</can_edit>
   <name>SendGrid NL Test</name>
   <text/>
   <newsletter_id>38074</newsletter_id>
   <total_recipients>1</total_recipients>
   <html/>
   <type>html</type>
   <date_schedule/>
   <identity>d22de3a53fac1abef944c80c19032c2c</identity>
   <subject/>
</newsletter>

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


{% anchor h2 %} list {% endanchor %}


Retrieve a list of all existing Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|No|Must be an existing Marketing Email|Search to see if a specific Marketing Email exists rather than a list of all Marketing Emails.|

{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/list.json?&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

<h3>Response: Success</h3>

{% codeblock lang:javascript %}
[
  {
    "name": "Just Testing",
    "newsletter_id": 560308
  },
  {
    "name": "LSRC",
    "newsletter_id": 560869
  },
  {
    "name": "LSRC test",
    "newsletter_id": 560908
  },
  {
    "name": "Test",
    "newsletter_id": 38074
  }
]
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
https://sendgrid.com/api/newsletter/list.xml?&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<newsletters>
   <newsletter>
      <name>Just Testing</name>
      <newsletter_id>560308</newsletter_id>
   </newsletter>
   <newsletter>
      <name>LSRC</name>
      <newsletter_id>560869</newsletter_id>
   </newsletter>
   <newsletter>
      <name>LSRC test</name>
      <newsletter_id>560908</newsletter_id>
   </newsletter>
   <newsletter>
      <name>Test</name>
      <newsletter_id>38074</newsletter_id>
   </newsletter>
</newsletters>

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


{% anchor h2 %} delete {% endanchor %}


Remove an existing Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|Remove the Marketing Email with this name.|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/delete.json?name=SendGrid_Test1&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/delete.xml?name=SendGrid_Test1&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

