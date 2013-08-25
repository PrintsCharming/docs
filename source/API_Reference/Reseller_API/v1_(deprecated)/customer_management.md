--- layout: page weight: 0 title: Customer Management navigation: show:
true ---

These are actions that directly affect your customer. We provide access
via XML and JSON.

* * * * *

{% anchor h2 %} Create a Customer {% endanchor %}

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
<td align="left">username</td>
<td align="left">Yes</td>
<td align="left">No more than 64 characters</td>
<td align="left">The customers new username</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">Yes</td>
<td align="left">Must be at least 6 characters</td>
<td align="left">New password of customer</td>
</tr>
<tr class="odd">
<td align="left">confirm_password</td>
<td align="left">Yes</td>
<td align="left">Must match password parameter, must be at least 6 characters</td>
<td align="left">Confirm new password</td>
</tr>
<tr class="even">
<td align="left">email</td>
<td align="left">Yes</td>
<td align="left">Must be in email format, no more than 64 characters</td>
<td align="left">Email address of new customer</td>
</tr>
<tr class="odd">
<td align="left">first_name</td>
<td align="left">Yes</td>
<td align="left">No more than 50 characters</td>
<td align="left">First name of new customer</td>
</tr>
<tr class="even">
<td align="left">last_name</td>
<td align="left">Yes</td>
<td align="left">No more than 50 characters</td>
<td align="left">Last name of new customer</td>
</tr>
<tr class="odd">
<td align="left">address</td>
<td align="left">Yes</td>
<td align="left">No more than 100 characters</td>
<td align="left">Address of new customer</td>
</tr>
<tr class="even">
<td align="left">city</td>
<td align="left">Yes</td>
<td align="left">No more than 100 characters</td>
<td align="left">City of new customer</td>
</tr>
<tr class="odd">
<td align="left">state</td>
<td align="left">Yes</td>
<td align="left">No more than 100 characters</td>
<td align="left">State of new customer</td>
</tr>
<tr class="even">
<td align="left">zip</td>
<td align="left">Yes</td>
<td align="left">No more than 50 characters</td>
<td align="left">Zip of new customer. This field is not validated for correct value. It's up to developer to check for valid zip code.</td>
</tr>
<tr class="odd">
<td align="left">country</td>
<td align="left">Yes</td>
<td align="left">No more than 100 characters</td>
<td align="left">Country of new customer</td>
</tr>
<tr class="even">
<td align="left">phone</td>
<td align="left">Yes</td>
<td align="left">No more than 50 characters</td>
<td align="left">Phone number of new customer</td>
</tr>
<tr class="odd">
<td align="left">website</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">Website of new customer</td>
</tr>
<tr class="even">
<td align="left">company</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">Company of new customer</td>
</tr>
<tr class="odd">
<td align="left">package</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">Name of the Package to assign to customer</td>
</tr>
<tr class="even">
<td align="left">whitelabel</td>
<td align="left">Yes</td>
<td align="left">No more than 255 characters</td>
<td align="left">The domain name for whitelabel</td>
</tr>
<tr class="odd">
<td align="left">ip_group[]</td>
<td align="left">No</td>
<td align="left">No more than 255 characters for each ip_group name. It must belong to you.</td>
<td align="left">Name of the IP Group you wish to optionally add.</td>
</tr>
<tr class="even">
<td align="left">ip[]</td>
<td align="left">No</td>
<td align="left">Valid ip address that belongs to you.</td>
<td align="left">If package allows it, you can optionally add additional IP addresses.</td>
</tr>
<tr class="odd">
<td align="left">free_user</td>
<td align="left">Maybe</td>
<td align="left">If the new customer is a free customer, you need to specify this parameter. Either true or false.</td>
<td align="left">Create a free customer</td>
</tr>
<tr class="even">
<td align="left">billing_date</td>
<td align="left">No</td>
<td align="left">If the new customer's billing anniversary date is on a different date from the time you create the customer, you need to specify this parameter. Must be in YYYY-mm-dd format. This date must be within one billing cycle from the time you create this customer. (e.g. if they sign up on 2/28/11, then the latest date you can use is 3/28/11)</td>
<td align="left">If the new customer's billing anniversary date is different from today (or when you execute this API call), you can specify the first billing anniversary date</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-555&free_user=tru
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=newcustomer@example.com&website=example.com&password=samplepassword&confirm_password=samplepassword&first_name=fname&last_name=lname&address=555_anystreet&city=any_city&state=CA&zip=91234&email=newcustomer@example.com&country=US&phone=555-55
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

* * * * *

{% anchor h2 %} Delete a Customer {% endanchor %}

Remove a customer from your account. This is **not** the same as
disabling a customer on our system. However, the removed user will still
be stored within the system so that you cannot re-register a new user
with this new username.

This is the same thing as closing out a customers account at the end of
their billing cycle.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Must be a customer registered under your account.</td>
<td align="left">The customers username you wish to delete.</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.delete.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.delete.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com
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

* * * * *

Retrieve Customers

Obtain a complete list of all customers.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <strong>get</strong> in order to retrieve user information</td>
</tr>
<tr class="even">
<td align="left">username</td>
<td align="left">No</td>
<td align="left">Search filter, customer that is registered under you</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">No</td>
<td align="left">Search filter, email address customer was registered with</td>
</tr>
<tr class="even">
<td align="left">active</td>
<td align="left">No</td>
<td align="left">Search filter, whether or not the customer is currently active</td>
</tr>
<tr class="odd">
<td align="left">first_name</td>
<td align="left">No</td>
<td align="left">Search filter, first name of customer</td>
</tr>
<tr class="even">
<td align="left">last_name</td>
<td align="left">No</td>
<td align="left">Search filter, last name of customer</td>
</tr>
<tr class="odd">
<td align="left">address</td>
<td align="left">No</td>
<td align="left">Search filter, address of customer</td>
</tr>
<tr class="even">
<td align="left">city</td>
<td align="left">No</td>
<td align="left">Search filter, city of customer</td>
</tr>
<tr class="odd">
<td align="left">state</td>
<td align="left">No</td>
<td align="left">Search filter, state of customer</td>
</tr>
<tr class="even">
<td align="left">country</td>
<td align="left">No</td>
<td align="left">Search filter, country of customer</td>
</tr>
<tr class="odd">
<td align="left">zip</td>
<td align="left">No</td>
<td align="left">Search filter, zipcode of customer</td>
</tr>
<tr class="even">
<td align="left">phone</td>
<td align="left">No</td>
<td align="left">Search filter, phone number of customer</td>
</tr>
<tr class="odd">
<td align="left">website</td>
<td align="left">No</td>
<td align="left">Search filter, website of customer</td>
</tr>
<tr class="even">
<td align="left">company</td>
<td align="left">No</td>
<td align="left">Search filter, company of customer</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>profile</em></td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=ge
{% endcodeblock %}

### Response

{% codeblock %}
<users><user><username>user1</username><email>example1@example.com</email><active>true</active><first_name>john</first_name><last_name>doe</last_name>

<address>
555 any street

</address>
<city>any
city</city><state>CA</state><zip>91234</zip><country>US</country><phone>555-555-5555</phone><website>example.com</website></user><user><username>user2</username><email>example2@example.com</email><active>false</active><first_name>jane</first_name><last_name>doe</last_name>

<address>
555 any street

</address>
<city>any
city</city><state>CA</state><zip>91234</zip><country>US</country><phone>555-555-5555</phone><website>example.com</website></user></users>JSON
Call

</h3>
{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=ge
{% endcodeblock %}

### Response

{% codeblock %}
{"username":"username","email":"example1@example.com","active":"true","first_name":"john","last_name":"doe","address":"555
any street","city":"any
city","state":"CA","zip":"91234","country":"US","phone":"555-555-5555","website":"example.com"},{"username":"username","email":"example2@example.com","active":"false","first_name":"jane","last_name":"doe","address":"555
any street","city":"any
city","state":"CA","zip":"91234","country":"US","phone":"555-555-5555","website":"example.com"}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Enable a Customer {% endanchor %}

Enable a customer so they may start sending out emails again. This call
will not enable website access.

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
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Must be in email format</td>
<td align="left">The customer you are planning to enabling</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>enable</em></td>
<td align="left">The customer you are planning to enabling</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=enable&user=customer@example.com
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
  "message": "User not found"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Disable a Customer {% endanchor %}

This prevents them from sending out emails with SendGrid.

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
<td align="left">username</td>
<td align="left">Yes</td>
<td align="left">Must be in email format</td>
<td align="left">The customer you are planning to disabling</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>disable</em></td>
<td align="left">The customer you are planning to disabling</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=disabl
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
  "message": "User not found"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Enable Website Access To A Customer {% endanchor %}

Allow a customer to login to the SendGrid.com website. This call will
not enable the customer from sending out emails.

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
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Must be in email format</td>
<td align="left">The customer you are planning to grant website access</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>website_enable</em></td>
<td align="left">The customer you are planning to grant website access</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_enable&user=customer@example.com
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
  "message": "User not found"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Disable Website Access To A Customer {% endanchor %}

Disallow a customer to login to the SendGrid.com website. This call will
not prevent them from sending out emails.

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
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Must be in email format</td>
<td align="left">The customer you are planning to disallow website access</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>website_disable</em></td>
<td align="left">The customer you are planning to disallow website access</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disable&user=customer@example.com
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
   <message>User not found</message>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=website_disabl
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
  "message": "User not found"
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Update Customer Profile {% endanchor %}

Allows you to update your customers profile information

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <strong>set</strong> in order to update profile information</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>profile</em></td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer that is registered under you</td>
</tr>
<tr class="even">
<td align="left">first_name</td>
<td align="left">No</td>
<td align="left">First name of customer</td>
</tr>
<tr class="odd">
<td align="left">last_name</td>
<td align="left">No</td>
<td align="left">Last name of customer</td>
</tr>
<tr class="even">
<td align="left">address</td>
<td align="left">No</td>
<td align="left">Address of customer</td>
</tr>
<tr class="odd">
<td align="left">city</td>
<td align="left">No</td>
<td align="left">City of customer</td>
</tr>
<tr class="even">
<td align="left">state</td>
<td align="left">No</td>
<td align="left">State of customer</td>
</tr>
<tr class="odd">
<td align="left">country</td>
<td align="left">No</td>
<td align="left">Country of customer</td>
</tr>
<tr class="even">
<td align="left">zip</td>
<td align="left">No</td>
<td align="left">Zipcode of customer</td>
</tr>
<tr class="odd">
<td align="left">phone</td>
<td align="left">No</td>
<td align="left">Phone number of customer</td>
</tr>
<tr class="even">
<td align="left">website</td>
<td align="left">No</td>
<td align="left">Website of customer</td>
</tr>
<tr class="odd">
<td align="left">company</td>
<td align="left">No</td>
<td align="left">Company of customer</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=set&user=customer@example.com&first_name=newFirstName&last_name=&newLastNam
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=set&user=customer@example.com&first_name=newFirstName&last_name=&newLastNam
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

* * * * *

{% anchor h2 %} Update Customer Password {% endanchor %}

Passwords are encrypted by default and therefore cannot be retrieved;
however, you can reset a customers password.

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
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under you</td>
<td align="left">The customer you are planning to reset the password</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">Yes</td>
<td align="left">Must be at least 6 characters</td>
<td align="left">New password of customer</td>
</tr>
<tr class="odd">
<td align="left">confirm_password</td>
<td align="left">Yes</td>
<td align="left">Must match password parameter and be at least 6 characters</td>
<td align="left">Confirm new password</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>password</em></td>
<td align="left">Allows you to access password functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=password&user=customer@example.com&password=newPasword&confirm_password=newPasswor
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=password&user=customer@example.com&password=newPasword&confirm_password=newPasswor
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

* * * * *

{% anchor h2 %} Update Customer Username {% endanchor %}

Note that your customer account username is used to login to our SMTP
server *and* the website and changes take effect immediately.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <strong>setUsername</strong></td>
<td align="left">This will let us know you want to update your customers username. This is the new username your customer will be authenticating with our SMTP servers <em>and</em> to access the website. This update takes effect immediately</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The user we will be updating their username for</td>
</tr>
<tr class="odd">
<td align="left">username</td>
<td align="left">Yes</td>
<td align="left">Must be in email format, not more than 100 characters, cannot be already taken and cannot contain SendGrid.com in the domain name</td>
<td align="left">This is the new username we will be authenticating with our SMTP servers <em>and</em> to access our site. This update takes effect immediately</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>profile</em></td>
<td align="left">Allows you to access profile functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setUsername&user=customer@example.com&username=newcustomer@example.com
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setUsername&user=customer@example.com&username=newcustomer@example.com
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

* * * * *

{% anchor h2 %} Update Customer Email Address {% endanchor %}

This is the contact email we use for your customers. Changes take place
immediately. It is your responsibility to validate the contact email.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <strong>setEmail</strong></td>
<td align="left">This will let us know you want to update your customers email address. This update takes effect immediately</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer must be registered under your account</td>
<td align="left">The user we will be updating their username for</td>
</tr>
<tr class="odd">
<td align="left">email</td>
<td align="left">Yes</td>
<td align="left">Must be in email format, not more than 100 characters</td>
<td align="left">This is the new email address we will use for contacting customer. This update takes effect immediately</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>password</em></td>
<td align="left">Allows you to access password functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com
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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON Call

{% codeblock %}
https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=profile&task=setEmail&user=customer@example.com&email=newcustomer@example.com
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
