---
layout: page
weight: 0
title: Authenticate a Customer Subuser
navigation:
   show: true
---

Authenticate a customer subuser on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Customer subuser that is registered under your account.</td>
      </tr>
      <tr>
         <td>password</td>
         <td>Yes</td>
         <td>Password the customer subuser submitted.</td>
      </tr>
   </tbody>
</table>


### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpassword&method=aut
{% endcodeblock %}
<h3>Response: Success</h3>
{% codeblock %}
result><message>success</message></result>
{% endcodeblock %}



### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      <error>... error messages ...</error>
   </errors>
</result>

{% endcodeblock %}




### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpassword&method=aut
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



