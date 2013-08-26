---
layout: page
weight: 0
title: Subusers
navigation:
   show: true
---

These are actions that directly affect your subuser. We provide access via XML and JSON.


{% info %} In both creating and searching for a subuser account, you are using the USERNAME parameter, while in all other cases you are using the USER parameter. When you are creating a subuser, there is no existing USER parameter to reference, so you are creating one. When you are searching for a subuser, you are authenticating to our servers with a valid username. {% endinfo %}
 
{% anchor h2 %} Create a Subuser {% endanchor %}


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
username

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 64 characters

</td>
<td markdown="1">
The subusers new username

</td>
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
New password of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
confirm_password

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must match password parameter, must be at least 6 characters

</td>
<td markdown="1">
Confirm new password

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format, no more than 64 characters

</td>
<td markdown="1">
Email address of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first_name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
First name of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
last_name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
Last name of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
address

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 100 characters

</td>
<td markdown="1">
Address of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
city

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 100 characters

</td>
<td markdown="1">
City of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
state

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 100 characters

</td>
<td markdown="1">
State of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
zip

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
Zip of new subuser. This field is not validated for correct value. It's up to developer to check for valid zip code.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
country

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 100 characters

</td>
<td markdown="1">
Country of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
phone

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
Phone number of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
website

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 255 characters

</td>
<td markdown="1">
Website of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
company

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 255 characters

</td>
<td markdown="1">
Company of new subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
mail_domain

</td>
<td markdown="1">
No

</td>
<td markdown="1">
A mail domain must already be setup with SendGrid, please contact [support@sendgrid.com](mailto:support@sendgrid.com) to have one setup

</td>
<td markdown="1">
Mail domain of new subuser

</td>
</tr>
</tbody>
</table>
{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=example@example.com&country=US&phone=555-5555 {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="create-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=example@example.com&country=US&phone=555-5555 {% endcodeblock %}

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
</div>

* * * * *


{% anchor h2 %} Delete a Subuser {% endanchor %}


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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be a valid subuser name.

</td>
<td markdown="1">
The subuser to delete.

</td>
</tr>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

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
</div>

* * * * *


{% anchor h2 %} Retrieve Subusers {% endanchor %}
 Obtain a complete list of all subusers.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to **get** in order to retrieve user information

</td>
</tr>
<tr markdown="1">
<td markdown="1">
username

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, subuser that is registered under you

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, email address subuser was registered with

</td>
</tr>
<tr markdown="1">
<td markdown="1">
active

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, whether or not the subuser is currently active

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, first name of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
last_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, last name of subuser

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
Search filter, address of subuser

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
Search filter, city of subuser

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
Search filter, state of subuser

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
Search filter, country of subuser

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
Search filter, zipcode of subuser

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
Search filter, phone number of subuser

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
Search filter, website of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
company

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, company of subuser

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>username</username>
      <email>example1@example.com</email>
      <active>true</active>
      <first_name>john</first_name>
      <last_name>doe</last_name>
      <address markdown="1">
555 any street

</address>
      <city>any city</city>
      <state>CA</state>
      <zip>91234</zip>
      <country>US</country>
      <phone>555-555-5555</phone>
      <website>example.com</website>
   </user>
   <user>
      <username>username</username>
      <email>example2@example.com</email>
      <active>false</active>
      <first_name>jane</first_name>
      <last_name>doe</last_name>
      <address markdown="1">
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
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
[
  {
    "username": "username",
    "email": "example1@example.com",
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
  },
  {
    "username": "username",
    "email": "example2@example.com",
    "active": "false",
    "first_name": "jane",
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
</div>

* * * * *


{% anchor h2 %} Enable a Subuser {% endanchor %}
 Enable a subuser so they may start sending out emails again. This call will not enable website access.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The subuser you are planning to enabling

</td>
</tr>
</tbody>
</table>
{% xmljsontabs enable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="enable-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.enable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="enable-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.enable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "User not found"
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Disable a Subuser {% endanchor %}
 This prevents them from sending out emails with SendGrid.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The subuser you are planning to disabling

</td>
</tr>
</tbody>
</table>
{% xmljsontabs disable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="disable-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.disable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="disable-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.disable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "User not found"
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Enable Website Access To A Subuser {% endanchor %}
 Allow a subuser to login to the SendGrid.com website. This call will not enable the subuser to send out emails.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The subuser you are planning to grant website access

</td>
</tr>
</tbody>
</table>
{% xmljsontabs enablewebsite %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="enablewebsite-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.website_enable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="enablewebsite-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.website_enable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "User not found"
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Disable Website Access To A Subuser {% endanchor %}
 Disallow a subuser to login to the SendGrid.com website. This call will not prevent them from sending emails.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The subuser you are planning to disallow website access

</td>
</tr>
</tbody>
</table>
{% xmljsontabs disablewebsite %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="disablewebsite-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.website_disable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="disablewebsite-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.website_disable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error


{% codeblock lang:javascript %}
{
  "message": "User not found"
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Update Subuser Profile {% endanchor %}
 Allows you to update your subusers profile information

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to **set** in order to update profile information

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser that is registered under you

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
First name of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
last_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Last name of subuser

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
Address of subuser

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
City of subuser

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
State of subuser

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
Country of subuser

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
Zipcode of subuser

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
Phone number of subuser

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
Website of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
company

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Company of subuser

</td>
</tr>
</tbody>
</table>
{% xmljsontabs updateprofile %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="updateprofile-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&first_name=newFirstName&last_name=&newLastNam {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="updateprofile-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&first_name=newFirstName&last_name=&newLastNam {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error

{% codeblock %} { "message": "error", "errors": [ "...error messages..." ] } {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Update Subuser Password {% endanchor %}
 Passwords are encrypted by default and therefore cannot be retrieved; however, you can reset a subusers password.

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
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under you

</td>
<td markdown="1">
The subuser you are planning to reset the password

</td>
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
New password of subuser

</td>
</tr>
<tr markdown="1">
<td markdown="1">
confirm_password

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must match password parameter and be at least 6 characters

</td>
<td markdown="1">
Confirm new password

</td>
</tr>
</tbody>
</table>
{% xmljsontabs updateSubuserPassword %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="updateSubuserPassword-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.password.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=newPasword&confirm_password=newPasswor {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="updateSubuserPassword-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.password.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=newPasword&confirm_password=newPasswor {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error

{% codeblock %} { "message": "error", "errors": [ "...error messages..." ] } {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Update Subuser Username {% endanchor %}
 Note that your subuser account username is used to login to our SMTP server *and* the website and changes take effect immediately.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to**setUsername**

</td>
<td markdown="1">
This will let us know you want to update your subusers username. This is the new username your subuser will be authenticating with our SMTP servers *and* to access the website. This update takes effect immediately

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The user we will be updating their username for

</td>
</tr>
<tr markdown="1">
<td markdown="1">
username

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format, not more than 100 characters, cannot be already taken and cannot contain SendGrid.com in the domain name

</td>
<td markdown="1">
This is the new username we will be authenticating with our SMTP servers *and* to access our site. This update takes effect immediately

</td>
</tr>
</tbody>
</table>
{% xmljsontabs updateSubuserUsername %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="updateSubuserUsername-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setUsername&user=example@example.com&username=newexample@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="updateSubuserUsername-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setUsername&user=example@example.com&username=newexample@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error

{% codeblock %} { "message": "error", "errors": [ "...error messages..." ] } {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Update Subuser Email Address {% endanchor %}
 This is the contact email we use for your subusers. Changes take place immediately. It is your responsibility to validate the contact email.

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
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to **setEmail**

</td>
<td markdown="1">
This will let us know you want to update your subusers email address. This update takes effect immediately

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
<td markdown="1">
The user we will be updating their username for

</td>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format, not more than 100 characters

</td>
<td markdown="1">
This is the new email address we will use for contacting subuser. This update takes effect immediately

</td>
</tr>
</tbody>
</table>
{% xmljsontabs updateSubuserEmailAddress %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="updateSubuserEmailAddress-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setEmail&user=example@example.com&email=newexample@example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="updateSubuserEmailAddress-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setEmail&user=example@example.com&email=newexample@example.com {% endcodeblock %}

### Response: Success

{% codeblock %} {"message":"success"} {% endcodeblock %}

### Response: Error

{% codeblock %} { "message": "error", "errors": [ "...error messages..." ] } {% endcodeblock %}

</div>
</div>

