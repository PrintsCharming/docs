---
layout: page
weight: 0
title: Authenticate a Customer Subuser
navigation:
   show: true
---

Authenticate a customer subuser on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer subuser that is registered under your account.</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">Yes</td>
<td align="left">Password the customer subuser submitted.</td>
</tr>
</tbody>
</table>

{% xmljsontabs auth %}

<div class="tab-content">
<div class="tab-pane" id="auth-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpassword&method=auth {% endcodeblock %}

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


</div>
<div class="tab-pane active" id="auth-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com&password=theirsubmittedpassword&method=auth {% endcodeblock %}

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
</div>

