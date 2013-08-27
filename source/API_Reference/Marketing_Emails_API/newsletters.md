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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>identity</td>
         <td>Yes</td>
         <td>Must be an existing Identity</td>
         <td>The Identity that will be used for the Marketing Email being created.</td>
      </tr>
      <tr>
         <td>name</td>
         <td>Yes</td>
         <td>None</td>
         <td>The name that will be used for the Marketing Email being created.</td>
      </tr>
      <tr>
         <td>subject</td>
         <td>Yes</td>
         <td>None</td>
         <td>The subject that will be used for the Marketing Email being created.</td>
      </tr>
      <tr>
         <td>text</td>
         <td>Yes</td>
         <td>None</td>
         <td>The text portion of the Marketing Email being created.</td>
      </tr>
      <tr>
         <td>html</td>
         <td>Yes</td>
         <td>None</td>
         <td>The html portion of the Marketing Email being created.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/add.json?identity=Sender_Address&amp;name=SendGrid_Test&amp;subject=testsubject&amp;text=testtextbody&amp;html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/add.xml?identity=Sender_Address&amp;name=SendGrid_Test&amp;subject=testsubject&amp;text=testtextbody&amp;html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Required</th>
      <th>Requirements</th>
      <th>Description</th>
   </tr>
   <td>name</td>
   <td>Yes</td>
   <td>Must be an existing Identity</td>
   <td>The name of the Marketing Email being updated.</td>
</table>

{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="edit-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/edit.json?identity=Sender_Address&amp;name=SendGrid_Edit_Test&amp;newname=new_name_test&amp;subject=test_subject&amp;text=test_text&amp;html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/edit.xml?identity=Sender_Address&amp;name=SendGrid_Edit_Test&amp;newname=new_name_test&amp;subject=test_subject&amp;text=test_text&amp;html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>name</td>
         <td>Yes</td>
         <td>Must be an existing Marketing Email</td>
         <td>Retrieve the content of an existing Marketing Email.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/get.json?name=SendGrid_Test&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/get.xml?name=SendGrid_Test&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>name</td>
         <td>No</td>
         <td>Must be an existing Marketing Email</td>
         <td>Search to see if a specific Marketing Email exists rather than a list of all Marketing Emails.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/list.json?&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/list.xml?&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>name</td>
         <td>Yes</td>
         <td>Must be an existing Marketing Email</td>
         <td>Remove the Marketing Email with this name.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/delete.json?name=SendGrid_Test1&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/delete.xml?name=SendGrid_Test1&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

