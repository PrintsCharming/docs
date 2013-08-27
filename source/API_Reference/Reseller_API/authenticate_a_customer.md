---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---

Authenticate a customer on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.

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
         <td>Customer that is registered under your account.</td>
      </tr>
      <tr>
         <td>password</td>
         <td>Yes</td>
         <td>Password the customer submitted.</td>
      </tr>
      <tr>
         <td>method</td>
         <td>Yes</td>
         <td>
            Must be set to
            <em>auth</em>
            . Allows you to access authentication functionality
         </td>
      </tr>
   </tbody>
</table>


{% xmljsontabs auth %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="auth-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;user=customer@example.com&amp;password=theirsubmittedpassword&amp;method=aut
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
<div markdown="1" class="tab-pane active" id="auth-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;user=customer@example.com&amp;password=theirsubmittedpassword&amp;method=aut
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

