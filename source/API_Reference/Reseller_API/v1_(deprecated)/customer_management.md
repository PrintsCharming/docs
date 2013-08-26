---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---

These are actions that directly affect your customer. We provide access via XML and JSON.

* * * * *


{% anchor h2 %} Create a Customer {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|username|Yes|No more than 64 characters|The customers new username|
|password|Yes|Must be at least 6 characters|New password of customer|
|confirm_password|Yes|Must match password parameter, must be at least 6 characters|Confirm new password|
|email|Yes|Must be in email format, no more than 64 characters|Email address of new customer|
|first_name|Yes|No more than 50 characters|First name of new customer|
|last_name|Yes|No more than 50 characters|Last name of new customer|
|address|Yes|No more than 100 characters|Address of new customer|
|city|Yes|No more than 100 characters|City of new customer|
|state|Yes|No more than 100 characters|State of new customer|
|zip|Yes|No more than 50 characters|Zip of new customer. This field is not validated for correct value. It's up to developer to check for valid zip code.|
|country|Yes|No more than 100 characters|Country of new customer|
|phone|Yes|No more than 50 characters|Phone number of new customer|
|website|Yes|No more than 255 characters|Website of new customer|
|company|Yes|No more than 255 characters|Company of new customer|
|package|Yes|No more than 255 characters|Name of the Package to assign to customer|
|whitelabel|Yes|No more than 255 characters|The domain name for whitelabel|
|ip_group[]|No|No more than 255 characters for each ip_group name. It must belong to you.|Name of the IP Group you wish to optionally add.|
|ip[]|No|Valid ip address that belongs to you.|If package allows it, you can optionally add additional IP addresses.|
|free_user|Maybe|If the new customer is a free customer, you need to specify this parameter. Either true or false.|Create a free customer|
|billing_date|No|If the new customer's billing anniversary date is on a different date from the time you create the customer, you need to specify this parameter. Must be in YYYY-mm-dd format. This date must be within one billing cycle from the time you create this customer. (e.g. if they sign up on 2/28/11, then the latest date you can use is 3/28/11)|If the new customer's billing anniversary date is different from today (or when you execute this API call), you can specify the first billing anniversary date|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-555&free_user=tru {% endcodeblock %}

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
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-55 {% endcodeblock %}

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


* * * * *


{% anchor h2 %} Delete a Customer {% endanchor %}


Remove a customer from your account. This is **not** the same as disabling a customer on our system. However, the removed user will still be stored within the system so that you cannot re-register a new user with this new username.

This is the same thing as closing out a customers account at the end of their billing cycle.

|Parameter|Required|Requirements|Parameter|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|task|Yes|Must be set to **get** in order to retrieve user information|
|username|No|Search filter, customer that is registered under you|
|email|No|Search filter, email address customer was registered with|
|active|No|Search filter, whether or not the customer is currently active|
|first_name|No|Search filter, first name of customer|
|last_name|No|Search filter, last name of customer|
|address|No|Search filter, address of customer|
|city|No|Search filter, city of customer|
|state|No|Search filter, state of customer|
|country|No|Search filter, country of customer|
|zip|No|Search filter, zipcode of customer|
|phone|No|Search filter, phone number of customer|
|website|No|Search filter, website of customer|
|company|No|Search filter, company of customer|
|method|Yes|Must be set to *profile*|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=ge {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<users>
   <user>
      <username>user1</username>
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
      <username>user2</username>
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


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=ge {% endcodeblock %}

### Response



* * * * *


{% anchor h2 %} Enable a Customer {% endanchor %}


Enable a customer so they may start sending out emails again. This call will not enable website access.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|user|Yes|Must be in email format|The customer you are planning to enabling|
|method|Yes|Must be set to *enable*|The customer you are planning to enabling|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com {% endcodeblock %}

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
   <message>User not found</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com {% endcodeblock %}

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


* * * * *


{% anchor h2 %} Disable a Customer {% endanchor %}


This prevents them from sending out emails with SendGrid.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|username|Yes|Must be in email format|The customer you are planning to disabling|
|method|Yes|Must be set to *disable*|The customer you are planning to disabling|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disable&user=customer@example.com {% endcodeblock %}

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
   <message>User not found</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disabl {% endcodeblock %}

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


* * * * *


{% anchor h2 %} Enable Website Access To A Customer {% endanchor %}


Allow a customer to login to the SendGrid.com website. This call will not enable the customer from sending out emails.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|user|Yes|Must be in email format|The customer you are planning to grant website access|
|method|Yes|Must be set to *website_enable*|The customer you are planning to grant website access|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com {% endcodeblock %}

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
   <message>User not found</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com {% endcodeblock %}

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


* * * * *


{% anchor h2 %} Disable Website Access To A Customer {% endanchor %}


Disallow a customer to login to the SendGrid.com website. This call will not prevent them from sending out emails.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|
|user|Yes|Must be in email format|The customer you are planning to disallow website access|
|method|Yes|Must be set to *website_disable*|The customer you are planning to disallow website access|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disable&user=customer@example.com {% endcodeblock %}

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
   <message>User not found</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disabl {% endcodeblock %}

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


* * * * *


{% anchor h2 %} Update Customer Profile {% endanchor %}


Allows you to update your customers profile information

|Parameter|Required|Description|
|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Management
navigation:
   show: true
---
----|
|task|Yes|Must be set to **setEmail**|This will let us know you want to update your customers email address. This update takes effect immediately|
|user|Yes|Customer must be registered under your account|The user we will be updating their username for|
|email|Yes|Must be in email format, not more than 100 characters|This is the new email address we will use for contacting customer. This update takes effect immediately|
|method|Yes|Must be set to *password*|Allows you to access password functionality|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com {% endcodeblock %}

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
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com {% endcodeblock %}

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

