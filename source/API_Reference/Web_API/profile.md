---
layout: page
weight: 0
title: Profile
navigation:
  show: true
---

View your SendGrid Profile

### There are no extra parameters required to view your profile information.

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
   <h3>Response</h3>

{% codeblock lang:javascript %}
[
  {
    "username": "sampleuser@example.com",
    "email": "sampleemail@example.com",
    "active": "true",
    "first_name": "john",
    "last_name": "doe",
    "address": "555 any street",
    "city": "any city",
    "state": "CA",
    "zip": "91234",
    "country": "US",
    "phone": "555-555-5555",
    "website": "example.com"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

		<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>sampleuser@example.com</username>
      <email>sampleemail@example.com</email>
      <active>true</active>
      <first_name>john</first_name>
      <last_name>doe</last_name>
      <address>555 any street</address>
      <city>any city</city>
      <state>CA</state>
      <zip>91234</zip>
      <country>US</country>
      <phone>555-555-5555</phone>
      <website>example.com</website>
   </user>
</users>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} set {% endanchor %}


<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
first\_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Your first name

</td>
</tr>
<tr markdown="1">
<td markdown="1">
last\_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Your last name

</td>
</tr>
<tr markdown="1">
<td markdown="1">
address

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Company address

</td>
</tr>
<tr markdown="1">
<td markdown="1">
city

</td>
<td markdown="1">
No

</td>
<td markdown="1">
City where your company is located

</td>
</tr>
<tr markdown="1">
<td markdown="1">
state

</td>
<td markdown="1">
No

</td>
<td markdown="1">
State where your company is located

</td>
</tr>
<tr markdown="1">
<td markdown="1">
country

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Country where your company is located

</td>
</tr>
<tr markdown="1">
<td markdown="1">
zip

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Zipcode where your company is located

</td>
</tr>
<tr markdown="1">
<td markdown="1">
phone

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Valid phone number where we can reach you

</td>
</tr>
<tr markdown="1">
<td markdown="1">
website

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Your company's website

</td>
</tr>
</tbody>
</table>
{% xmljsontabs set %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="set-json">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&first_name=newFirstName&last_name=&newLastName
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
<div markdown="1" class="tab-pane" id="set-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&first_name=newFirstName&last_name=&newLastName
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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
   @nodes
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} setPassword {% endanchor %}


<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
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
<tr markdown="1">
<td markdown="1">
password

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be at least 6 characters

</td>
<td markdown="1">
Your new password

</td>
</tr>
<tr markdown="1">
<td markdown="1">
confirm\_password

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must match password parameter and be at least 6 characters long

</td>
<td markdown="1">
Confrim new password

</td>
</tr>
</tbody>
</table>
{% xmljsontabs reset %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="reset-json">
### Call



{% codeblock %}
https://sendgrid.com/api/password.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&password=newPasword&confirm_password=newPassword
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
<div markdown="1" class="tab-pane" id="reset-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/password.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&password=newPasword&confirm_password=newPassword
{% endcodeblock %}

<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error



{% codeblock %}
<result>
  <message>error</message>
  <errors>
    ...
    <error>... error messages ...</error>
    ...
  </errors>
@nodes
{% endcodeblock %}

  </div>
</div>

<hr/>



 
{% anchor h2 %}
setUsername 
{% endanchor %}
 

{% warning %}
Please note, your account username is used to login to our SMTP server and the website. Changes will take effect immediately.
{% endwarning %}


 <table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>username</td>
         <td>Yes</td>
         <td>Must not exceed 100 characters. The username cannot be already taken or       contain the SendGrid.com domain</td>
         <td>This is the new username we will be authenticating with our SMTP servers and       our website. Changes take effect immediately</td>
      </tr>
   </tbody>
</table>



{% xmljsontabs setusername %}

<div class="tab-content">
  <div class="tab-pane active" id="setusername-json">
   <h3>Call</h3>
{% codeblock %}
https://sendgrid.com/api/profile.setUsername.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=yournewusername@domain.com
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
<div markdown="1" class="tab-pane" id="setusername-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.setUsername.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=yournewusername@domain.com
{% endcodeblock %}
<h3>Response: Success</H3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




### Response: Error



{% codeblock %}
<result>
  <message>error</message>
  <errors>
    ...
    <error>... error messages ...</error>
    ...
  </errors>
@nodes
{% endcodeblock %}

  </div>
</div>

<hr/>



{% anchor h2 %}
setEmail 
{% endanchor %}



{% info %}
Please note, we send out a confirmation email to the new email account in order to be validated. Your email address changes when you click on the confirmation link.
{% endinfo %}


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>email</td>
         <td>Yes</td>
         <td>Must be in email format and not more than 100 characters</td>
         <td>This is the new email address we will be contacting you with. Changes take      effect immediately</td>
      </tr>
   </tbody>
</table>



{% xmljsontabs setemail %}

<div class="tab-content">
  <div class="tab-pane active" id="setemail-json">
   <h3>Call</h3>
{% codeblock %}
https://sendgrid.com/api/profile.setEmail.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=yournewemail@domain.com
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
<div markdown="1" class="tab-pane" id="setemail-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/profile.setEmail.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=yournewemail@domain.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<message>success</message>

{% endcodeblock %}




Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<message>error</message>

{% endcodeblock %}




</div>
</div>

