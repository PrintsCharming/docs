---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
These are actions that directly affect your customer. We provide access via XML and JSON. 
{% anchor h2 %} Create a Customer {% endanchor %}


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
The customers new username

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
New password of customer

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
Email address of new customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first\_name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
First name of new customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
last\_name

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 50 characters

</td>
<td markdown="1">
Last name of new customer

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
Address of new customer

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
City of new customer

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
State of new customer

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
Zip of new customer. This field is not validated for correct value. It's up to developer to check for valid zip code.

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
Country of new customer

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
Phone number of new customer

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
Website of new customer

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
Company of new customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
package

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 255 characters

</td>
<td markdown="1">
Name of the Package to assign to customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
whitelabel

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
No more than 255 characters

</td>
<td markdown="1">
The domain name for whitelabel

</td>
</tr>
<tr markdown="1">
<td markdown="1">
ip\_group[]

</td>
<td markdown="1">
No

</td>
<td markdown="1">
No more than 255 characters for each ip\_group name. It must belong to you.

</td>
<td markdown="1">
Name of the IP Group you wish to optionally add.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
ip[]

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Valid ip address that belongs to you.

</td>
<td markdown="1">
If package allows it, you can optionally add additional IP addresses.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
free\_user

</td>
<td markdown="1">
Maybe

</td>
<td markdown="1">
If the new customer is a free customer, you need to specify this parameter. Either true or false.

</td>
<td markdown="1">
Create a free customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
billing\_date

</td>
<td markdown="1">
No

</td>
<td markdown="1">
If the new customer's billing anniversary date is on a different date from the time you create the customer, you need to specify this parameter. Must be in YYYY-mm-dd format. This date must be within one billing cycle from the time you create this customer. (e.g. if they sign up on 2/28/11, then the latest date you can use is 3/28/11)

</td>
<td markdown="1">
If the new customer's billing anniversary date is different from today (or when you execute this API call), you can specify the first billing anniversary date

</td>
</tr>
</tbody>
</table>
{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-555&free_user=tru
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-55
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
</div>

* * * * *


{% anchor h2 %} Delete a Customer {% endanchor %}
 Remove a customer from your account. This is **not** the same as disabling a customer on our system. However, the removed user will still be stored within the system so that you cannot re-register a new user with this new username. This is the same thing as closing out a customers account at the end of their billing cycle.

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
Parameter

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
Must be a customer registered under your account.

</td>
<td markdown="1">
The customers username you wish to delete.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com
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
</div>

* * * * *

Retrieve Customers

Obtain a complete list of all customers.

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
Must be set to **get** in order to retrieve user information

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
Search filter, customer that is registered under you

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
Search filter, email address customer was registered with

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
Search filter, whether or not the customer is currently active

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first\_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Search filter, first name of customer

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
Search filter, last name of customer

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
Search filter, address of customer

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
Search filter, city of customer

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
Search filter, state of customer

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
Search filter, country of customer

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
Search filter, zipcode of customer

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
Search filter, phone number of customer

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
Search filter, website of customer

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
Search filter, company of customer

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *profile*

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=ge
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>user1</username>
      <email>example1@example.com</email>
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
   <user>
      <username>user2</username>
      <email>example2@example.com</email>
      <active>false</active>
      <first_name>jane</first_name>
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
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=get
{% endcodeblock %}
<h3>Response</h3>

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


{% anchor h2 %} Enable a Customer {% endanchor %}
 Enable a customer so they may start sending out emails again. This call will not enable website access.

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
The customer you are planning to enabling

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *enable*

</td>
<td markdown="1">
The customer you are planning to enabling

</td>
</tr>
</tbody>
</table>
{% xmljsontabs enable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="enable-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="enable-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com
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
  "message": "User not found"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Disable a Customer {% endanchor %}
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
username

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be in email format

</td>
<td markdown="1">
The customer you are planning to disabling

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *disable*

</td>
<td markdown="1">
The customer you are planning to disabling

</td>
</tr>
</tbody>
</table>
{% xmljsontabs disable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="disable-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="disable-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disabl
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
  "message": "User not found"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Enable Website Access To A Customer {% endanchor %}
 Allow a customer to login to the SendGrid.com website. This call will not enable the customer from sending out emails.

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
The customer you are planning to grant website access

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *website\_enable*

</td>
<td markdown="1">
The customer you are planning to grant website access

</td>
</tr>
</tbody>
</table>
{% xmljsontabs website %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="website-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="website-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com
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
  "message": "User not found"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Disable Website Access To A Customer {% endanchor %}
 Disallow a customer to login to the SendGrid.com website. This call will not prevent them from sending out emails.

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
The customer you are planning to disallow website access

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *website\_disable*

</td>
<td markdown="1">
The customer you are planning to disallow website access

</td>
</tr>
</tbody>
</table>
{% xmljsontabs unwebsite %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="unwebsite-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="unwebsite-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disabl
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
  "message": "User not found"
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Update Customer Profile {% endanchor %}
 Allows you to update your customers profile information

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
Must be set to **set** in order to update profile information

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *profile*

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
Customer that is registered under you

</td>
</tr>
<tr markdown="1">
<td markdown="1">
first\_name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
First name of customer

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
Last name of customer

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
Address of customer

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
City of customer

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
State of customer

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
Country of customer

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
Zipcode of customer

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
Phone number of customer

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
Website of customer

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
Company of customer

</td>
</tr>
</tbody>
</table>
{% xmljsontabs update %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="update-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=set&user=customer@example.com&first_name=newFirstName&last_name=&newLastNam
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="update-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=set&user=customer@example.com&first_name=newFirstName&last_name=&newLastNam
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
</div>

* * * * *


{% anchor h2 %} Update Customer Password {% endanchor %}
 Passwords are encrypted by default and therefore cannot be retrieved; however, you can reset a customers password.

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
Customer must be registered under you

</td>
<td markdown="1">
The customer you are planning to reset the password

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
New password of customer

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
Must match password parameter and be at least 6 characters

</td>
<td markdown="1">
Confirm new password

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *password*

</td>
<td markdown="1">
Allows you to access password functionality

</td>
</tr>
</tbody>
</table>
{% xmljsontabs password %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="password-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=password&user=customer@example.com&password=newPasword&confirm_password=newPasswor
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="password-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=password&user=customer@example.com&password=newPasword&confirm_password=newPasswor
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
</div>

* * * * *


{% anchor h2 %} Update Customer Username {% endanchor %}
 Note that your customer account username is used to login to our SMTP server *and* the website and changes take effect immediately.

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
Must be set to **setUsername**

</td>
<td markdown="1">
This will let us know you want to update your customers username. This is the new username your customer will be authenticating with our SMTP servers *and* to access the website. This update takes effect immediately

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
Customer must be registered under your account

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
This is the new username we will be authenticating with our SMTP servers *and* to access our site. This update takes effect immediately

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *profile*

</td>
<td markdown="1">
Allows you to access profile functionality

</td>
</tr>
</tbody>
</table>
{% xmljsontabs name %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="name-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setUsername&user=customer@example.com&username=newcustomer@example.com
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="name-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setUsername&user=customer@example.com&username=newcustomer@example.com
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
</div>

* * * * *


{% anchor h2 %} Update Customer Email Address {% endanchor %}
 This is the contact email we use for your customers. Changes take place immediately. It is your responsibility to validate the contact email.

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
Must be set to **setEmail**

</td>
<td markdown="1">
This will let us know you want to update your customers email address. This update takes effect immediately

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
Customer must be registered under your account

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
This is the new email address we will use for contacting customer. This update takes effect immediately

</td>
</tr>
<tr markdown="1">
<td markdown="1">
method

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *password*

</td>
<td markdown="1">
Allows you to access password functionality

</td>
</tr>
</tbody>
</table>
{% xmljsontabs email %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="email-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com
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
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="email-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com
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
</div>

