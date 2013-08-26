---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
These are actions that directly affect your customer. We provide access via XML and JSON. 
{% anchor h2 %} Create a Customer {% endanchor %}



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

