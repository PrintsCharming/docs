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



{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=example@example.com&country=US&phone=555-5555
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
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=example@example.com&country=US&phone=555-5555
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


{% anchor h2 %} Delete a Subuser {% endanchor %}



{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example@example.com
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
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
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


{% anchor h2 %} Retrieve Subusers {% endanchor %}
 Obtain a complete list of all subusers.


{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>username</username>
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
      <username>username</username>
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
https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get
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


{% anchor h2 %} Enable a Subuser {% endanchor %}
 Enable a subuser so they may start sending out emails again. This call will not enable website access.


{% xmljsontabs enable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="enable-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.enable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
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
<div markdown="1" class="tab-pane active" id="enable-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.enable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
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


{% anchor h2 %} Disable a Subuser {% endanchor %}
 This prevents them from sending out emails with SendGrid.


{% xmljsontabs disable %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="disable-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.disable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane active" id="disable-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.disable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
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


{% anchor h2 %} Enable Website Access To A Subuser {% endanchor %}
 Allow a subuser to login to the SendGrid.com website. This call will not enable the subuser to send out emails.


{% xmljsontabs enablewebsite %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="enablewebsite-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.website_enable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
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
<div markdown="1" class="tab-pane active" id="enablewebsite-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.website_enable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
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


{% anchor h2 %} Disable Website Access To A Subuser {% endanchor %}
 Disallow a subuser to login to the SendGrid.com website. This call will not prevent them from sending emails.


{% xmljsontabs disablewebsite %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="disablewebsite-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.website_disable.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane active" id="disablewebsite-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.website_disable.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
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


{% anchor h2 %} Update Subuser Profile {% endanchor %}
 Allows you to update your subusers profile information


{% xmljsontabs updateprofile %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="updateprofile-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&first_name=newFirstName&last_name=&newLastNam
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
<div markdown="1" class="tab-pane active" id="updateprofile-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=set&user=example@example.com&first_name=newFirstName&last_name=&newLastNam
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
{% endcodeblock %}



### Response: Error



{% codeblock %}
{
    "message": "error",
    "errors": [
        "...error messages..."
    ]
}
{% endcodeblock %}
  </div>
</div>
  <hr/>
  
{% anchor h2 %}
Update Subuser Password 
{% endanchor %}

  Passwords are encrypted by default and therefore cannot be retrieved; however, you can reset a subusers password.
  
  
{% xmljsontabs updateSubuserPassword %}

<div class="tab-content">
  <div class="tab-pane" id="updateSubuserPassword-xml">
<h3>Call</h3>
  {% codeblock %}
https://sendgrid.com/apiv2/customer.password.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=newPasword&confirm_password=newPasswor
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
<div markdown="1" class="tab-pane active" id="updateSubuserPassword-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.password.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=newPasword&confirm_password=newPasswor
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
{% endcodeblock %}



### Response: Error



{% codeblock %}
{
    "message": "error",
    "errors": [
        "...error messages..."
    ]
}
{% endcodeblock %}
  </div>
</div>
  <hr/>
  
{% anchor h2 %}
Update Subuser Username 
{% endanchor %}

  Note that your subuser account username is used to login to our SMTP server <em>and</em> the website and changes take effect immediately.
  
  
{% xmljsontabs updateSubuserUsername %}

<div class="tab-content">
  <div class="tab-pane" id="updateSubuserUsername-xml">
<h3>Call</h3>
  {% codeblock %}
https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setUsername&user=example@example.com&username=newexample@example.com
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
<div markdown="1" class="tab-pane active" id="updateSubuserUsername-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.profile.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setUsername&user=example@example.com&username=newexample@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
{% endcodeblock %}



### Response: Error



{% codeblock %}
{
    "message": "error",
    "errors": [
        "...error messages..."
    ]
}
{% endcodeblock %}
  </div>
</div>
  <hr/>
  
{% anchor h2 %}
Update Subuser Email Address 
{% endanchor %}

  This is the contact email we use for your subusers. Changes take place immediately. It is your responsibility to validate the contact email.
  
  
{% xmljsontabs updateSubuserEmailAddress %}

<div class="tab-content">
  <div class="tab-pane" id="updateSubuserEmailAddress-xml">
<h3>Call</h3>
  {% codeblock %}
https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setEmail&user=example@example.com&email=newexample@example.com
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
<div markdown="1" class="tab-pane active" id="updateSubuserEmailAddress-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.profile.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=setEmail&user=example@example.com&email=newexample@example.com
{% endcodeblock %}
<h3>Response: Success</h3>
  {% codeblock %}
{"message":"success"}
{% endcodeblock %}



### Response: Error

{% codeblock %} { "message": "error", "errors": [ "...error messages..." ] } {% endcodeblock %}

</div>
</div>

