---
layout: page
weight: 0
title: Authenticate a Subuser
navigation:
   show: true
---

<span>Authenticate a subuser on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.</span>

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>Subuser that is registered under your account.</td>
      </tr>
      <tr>
         <td>password</td>
         <td>Yes</td>
         <td>Password the subuser submitted.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs auth %}

<div class="tab-content">
<div class="tab-pane active" id="auth-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.auth.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpassword
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
<div class="tab-pane" id="auth-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/customer.auth.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpasswor
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
      <error> ... error messages ... </error>
      ...
   </errors>
</result>

{% endcodeblock %}

</div>
</div>

