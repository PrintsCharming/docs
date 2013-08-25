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

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.get.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response

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
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.get.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>sampleuser@example.com</username>
      <email>sampleemail@example.com</email>
      <active>true</active>
      <first_name>john</first_name>
      <last_name>doe</last_name>
      <address>
555 any street

</address>
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


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>first\_name</td>
         <td>No</td>
         <td>Your first name</td>
      </tr>
      <tr>
         <td>last\_name</td>
         <td>No</td>
         <td>Your last name</td>
      </tr>
      <tr>
         <td>address</td>
         <td>No</td>
         <td>Company address</td>
      </tr>
      <tr>
         <td>city</td>
         <td>No</td>
         <td>City where your company is located</td>
      </tr>
      <tr>
         <td>state</td>
         <td>No</td>
         <td>State where your company is located</td>
      </tr>
      <tr>
         <td>country</td>
         <td>No</td>
         <td>Country where your company is located</td>
      </tr>
      <tr>
         <td>zip</td>
         <td>No</td>
         <td>Zipcode where your company is located</td>
      </tr>
      <tr>
         <td>phone</td>
         <td>No</td>
         <td>Valid phone number where we can reach you</td>
      </tr>
      <tr>
         <td>website</td>
         <td>No</td>
         <td>Your company's website</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs set %}

<div class="tab-content">
<div class="tab-pane active" id="set-json">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&first_name=newFirstName&last_name=&newLastName
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
<div class="tab-pane" id="set-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&first_name=newFirstName&last_name=&newLastName
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


<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>password</td>
         <td>Yes</td>
         <td>Must be at least 6 characters</td>
         <td>Your new password</td>
      </tr>
      <tr>
         <td>confirm\_password</td>
         <td>Yes</td>
         <td>Must match password parameter and be at least 6 characters long</td>
         <td>Confrim new password</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs reset %}

<div class="tab-content">
<div class="tab-pane active" id="reset-json">
### Call

{% codeblock %}
https://sendgrid.com/api/password.set.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&password=newPasword&confirm_password=newPassword
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
<div class="tab-pane" id="reset-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/password.set.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&password=newPasword&confirm_password=newPassword
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock %}
<result> <message>error</message> <errors> ... <error>... error messages ...</error> ... </errors> @nodes
{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} setUsername {% endanchor %}
 
{% warning %} Please note, your account username is used to login to our SMTP server and the website. Changes will take effect immediately. {% endwarning %}


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
         <td>Must not exceed 100 characters. The username cannot be already taken or contain the SendGrid.com domain</td>
         <td>This is the new username we will be authenticating with our SMTP servers and our website. Changes take effect immediately</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs setusername %}

<div class="tab-content">
<div class="tab-pane active" id="setusername-json">
### Call

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
<div class="tab-pane" id="setusername-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.setUsername.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=yournewusername@domain.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

### Response: Error

{% codeblock %}
<result> <message>error</message> <errors> ... <error>... error messages ...</error> ... </errors> @nodes
{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} setEmail {% endanchor %}
 
{% info %} Please note, we send out a confirmation email to the new email account in order to be validated. Your email address changes when you click on the confirmation link. {% endinfo %}


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
         <td>This is the new email address we will be contacting you with. Changes take effect immediately</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs setemail %}

<div class="tab-content">
<div class="tab-pane active" id="setemail-json">
### Call

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
<div class="tab-pane" id="setemail-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/profile.setEmail.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&email=yournewemail@domain.com
{% endcodeblock %}

### Response: Success

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

