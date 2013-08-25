--- layout: page weight: 0 title: Marketing Emails navigation: show:
true ---

This endpoint allows you to add, view, or remove marketing emails.

{% anchor h2 %} add {% endanchor %}

Create a new Marketing Email.

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
<td align="left">identity</td>
<td align="left">Yes</td>
<td align="left">Must be an existing Identity</td>
<td align="left">The Identity that will be used for the Marketing Email being created.</td>
</tr>
<tr class="even">
<td align="left">name</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The name that will be used for the Marketing Email being created.</td>
</tr>
<tr class="odd">
<td align="left">subject</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The subject that will be used for the Marketing Email being created.</td>
</tr>
<tr class="even">
<td align="left">text</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The text portion of the Marketing Email being created.</td>
</tr>
<tr class="odd">
<td align="left">html</td>
<td align="left">Yes</td>
<td align="left">None</td>
<td align="left">The html portion of the Marketing Email being created.</td>
</tr>
</tbody>
</table>

{% xmljsontabs create %}

<div class="tab-content">
<div class="tab-pane active" id="create-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/add.json?identity=Sender_Address&name=SendGrid_Test&subject=testsubject&text=testtextbody&html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div class="tab-pane" id="create-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/add.xml?identity=Sender_Address&name=SendGrid_Test&subject=testsubject&text=testtextbody&html=%3Chtml%3E%3Cp%3Etest_html_body%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

<div class="tab-content">
<div class="tab-pane active" id="edit-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/edit.json?identity=Sender_Address&name=SendGrid_Edit_Test&newname=new_name_test&subject=test_subject&text=test_text&html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/edit.xml?identity=Sender_Address&name=SendGrid_Edit_Test&newname=new_name_test&subject=test_subject&text=test_text&html=%3Chtml%3E%3Cp%3ETest_html_text%3C%2Fp%3E%3C%2Fhtml%3E&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

Retrieve the contents of an existing Marketing Email.

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
<td align="left">Retrieve the content of an existing Marketing Email.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/get.json?name=SendGrid_Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/get.xml?name=SendGrid_Test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<newsletter>
   <can_edit>True</can_edit>
   <name>SendGrid NL Test</name>
   <text/>
   <newsletter_id>38074</newsletter_id>
   <total_recipients>1</total_recipients>
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
<td align="left">No</td>
<td align="left">Must be an existing Marketing Email</td>
<td align="left">Search to see if a specific Marketing Email exists rather than a list of all Marketing Emails.</td>
</tr>
</tbody>
</table>

{% xmljsontabs list %}

<div class="tab-content">
<div class="tab-pane active" id="list-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/list.json?&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

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
<div class="tab-pane" id="list-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/list.xml?&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

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
<td align="left">Remove the Marketing Email with this name.</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/delete.json?name=SendGrid_Test1&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/delete.xml?name=SendGrid_Test1&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

