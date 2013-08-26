---
layout: page
weight: 0
title: Multiple Credentials
navigation:
  show: true
---

{% anchor h2 %} Add user credential {% endanchor %}


Notes: This API call allows SendGrid resellers to add a new set of credentials to a specified child account.


### XML API Request



{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=add&credential_name=reseller_customer_credential&credential_password=reseller_customer_password
{% endcodeblock %}
<h4>Return - Success</h4>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




#### Return - Error




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

<h3>JSON API Request</h3>
{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=add&credential_name=reseller_customer_credential&credential_password=reseller_customer_password
{% endcodeblock %}



#### Return - Success




{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




#### Return - Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




* * * * *


{% anchor h2 %} Edit user credential {% endanchor %}


Notes: This API call allows SendGrid resellers to edit an already existing credential password. Changing the credential name is not currently allowed.


### XML API Request



{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=edit&credential_name=reseller_customer_credential&new_credential_password=reseller_customer_password
{% endcodeblock %}
<h4>Return - Success</h4>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




#### Return - Error




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




### JSON API Request



{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=edit&credential_name=reseller_customer_credential&new_credential_password=reseller_customer_password
{% endcodeblock %}

<h4>Return - Success</h4>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




#### Return - Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}




</h4>

{% anchor h2 %} Delete user credential {% endanchor %}


Notes: This API call allows SendGrid resellers to delete an existing credential under a child account.


### XML API Request



{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=delete&credential_name=reseller_customer_credential
{% endcodeblock %}
<h4>Return - Success</h4>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}




#### Return - Error




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




### JSON API Request



{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=delete&credential_name=reseller_customer_credential
{% endcodeblock %}

<h4>Return - Success</h4>

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}




#### Return - Error




{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}



