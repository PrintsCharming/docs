--- layout: page weight: 0 title: Sender Address navigation: show: true
---

This endpoint allows you to manage and create Sender Addresses (formerly
Identities) associated with the Marketing Email feature.

{% anchor h2 %} add {% endanchor %}

Create a new Address.

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Required</th>
      <th>Requirements</th>
      <th>Description</th>
   </tr>
   <tr>
      <td>Identity</td>
      <td>Yes</td>
      <td>None</td>
      <td>Create an Address named this.</td>
   </tr>
   <tr>
      <td>name</td>
      <td>Yes</td>
      <td>None</td>
      <td>Specify the name to be used for this Address.</td>
   </tr>
   <tr>
      <td>email</td>
      <td>Yes</td>
      <td>Email address format, complying with [RFC5322](http://tools.ietf.org/html/rfc5322)</td>
      <td>Specify the email address to be used for this Address.</td>
   </tr>
   <tr>
      <td>replyto</td>
      <td>No</td>
      <td>Email address format, complying with [RFC5322](http://tools.ietf.org/html/rfc5322)</td>
      <td>Specify an email address to be used in the Reply-To field. If notdefined, will default to the *email* parameter.</td>
   </tr>
   <tr>
      <td>address</td>
      <td>Yes</td>
      <td>None</td>
      <td>Specify the physical address to be used for this Address.</td>
   </tr>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/add.json?identity=Sender_Address1&name=Grant&email=grant.hull%40sendgrid.com&address=929_Pearl_Stree&city=Boulder&state=Colorado&zip=80302&country=US&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/identity/add.xml?identity=Sender_Address1&name=Grant&email=grant.hull%40sendgrid.com&address=929_Pearl_Stree&city=Boulder&state=Colorado&zip=80302&country=US&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

Edit an existing Address.

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Required</th>
      <th>Requirements</th>
      <th>Description</th>
   </tr>
   <tr>
      <td>Identity</td>
      <td>Yes</td>
      <td>Must be an existing Address.</td>
      <td>The Address you wish to edit.</td>
   </tr>
   <tr>
      <td>newidentity</td>
      <td>No</td>
      <td>None</td>
      <td>Specify the new name to be used for this Address.</td>
   </tr>
   <tr>
      <td>name</td>
      <td>No</td>
      <td>None</td>
      <td>Specify the new name to be used for this Address.</td>
   </tr>
   <tr>
      <td>email</td>
      <td>Yes</td>
      <td>Email address format, complying with [RFC5322](http://tools.ietf.org/html/rfc5322)</td>
      <td>Specify the email address to be used for this Address.</td>
   </tr>
   <tr>
      <td>replyto</td>
      <td>No</td>
      <td>Email address format, complying with [RFC5322](http://tools.ietf.org/html/rfc5322)</td>
      <td>Specify an email address to be used in the Reply-To field. If notdefined, will default to the *email* parameter.</td>
   </tr>
   <tr>
      <td>address</td>
      <td>No</td>
      <td>None</td>
      <td>Specify the new physical address to be used for this Address.</td>
   </tr>
</table>

{% xmljsontabs edit %}

<div class="tab-content">
<div class="tab-pane active" id="edit-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/edit.json?identity=Sender_Address2&newidentity=Sender_Address3&name=Grant&email=grant.hull%40sendgrid.com&address=929_Pearl_Street&city=Boulder&state=Colorado&zip=80302&country=US&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/identity/edit.xml?identity=Sender_Address2&newidentity=Sender_Address3&name=Grant&email=grant.hull%40sendgrid.com&address=929_Pearl_Street&city=Boulder&state=Colorado&zip=80302&country=US&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

Retrieve information associated with a particular Address.

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
<td align="left">Must be an existing Address.</td>
<td align="left">Retrieve contents of the specified Address.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/get.json?identity=Sender_Address&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
{
  "city": "Boulder",
  "name": "Name",
  "zip": "80302",
  "replyto": "Email Address",
  "country": "US",
  "state": "CO",
  "address": "929 Pearl Street ste 200 ",
  "email": "example@sendgrid.com",
  "identity": "Sender_Address "
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

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/get.xml?identity=Sender_Address&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<identity>
   <city>Boulder</city>
   <name>Example Name</name>
   <zip>80302</zip>
   <replyto>example@sendgrid.com</replyto>
   <country>US</country>
   <state>CO</state>
   <address>
929 Pearl Street ste 200

</address>
   <email>example@sendgrid.com</email>
   <identity>Sender\_Address
</identity>
</identity>

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

List all Addresses on your account, or check if a particular Address
exists.

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
<td align="left">No</td>
<td align="left">Must be an existing Address.</td>
<td align="left">Check for this particular Identity. (To list all Addresses on your account exclude this parameter)</td>
</tr>
</tbody>
</table>

{% xmljsontabs list %}

<div class="tab-content">
<div class="tab-pane active" id="list-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/list.json?identity=Sender_Address4&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "identity": "Sender_Address4"
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
https://sendgrid.com/api/newsletter/identity/list.xml?identity=Sender_Address4&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

<identities>
   <identity>
      <identity>Sender\_Address4</identity>
   </identity>
</identities>

{% endcodeblock %}

</div>
</div>

* * * * *

{% anchor h2 %} delete {% endanchor %}

Remove an Address from your account.

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
<td align="left">Must be an existing Address.</td>
<td align="left">Remove the specified Address from your account.</td>
</tr>
</tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/identity/delete.json?identity=Sender_Address4&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/identity/delete.xml?identity=Sender_Address4&api_user=your_sendgrid_username&api_key=your_sendgrid_password
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

