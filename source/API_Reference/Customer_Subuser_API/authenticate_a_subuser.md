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

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="auth-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.auth.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;user=example@example.com&amp;password=theirsubmittedpassword
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
<div markdown="1" class="tab-pane" id="auth-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.auth.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;user=example@example.com&amp;password=theirsubmittedpasswor
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
      <error>
          ... 
    error messages 
    ...
        </error>
      ...
   </errors>
</result>

{% endcodeblock %}




</div>
</div>

