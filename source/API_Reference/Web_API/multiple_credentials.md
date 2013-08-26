---
layout: page
weight: 0
title: Multiple Credentials
navigation:
  show: true
---

Get---
layout: page
weight: 0
title: Multiple Credentials
navigation:
  show: true
---

This API call allows user to add a new set of credentials to their account.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>api_user</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The primary account holder's user ID creating the new account</td>
      </tr>
      <tr>
         <td>api_key</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The primary account holder's password</td>
      </tr>
      <tr>
         <td>username</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>Enter a username for the new account</td>
      </tr>
      <tr>
         <td>password</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>Enter a password for the new account</td>
      </tr>
      <tr>
         <td>permissions</td>
         <td>No</td>
         <td>JSON array of bits</td>
         <td>Credentials are specified using a JSON object. There are three key names: **email** for access to SMTP, **api** for programmatic access, and **web** for administration. The values for each are a bit, 0 for off or 1 for on.The following example allows the specified username/password to log into the dashboard, but *not* send email or have access to any of the APIs:`{"email": 0, "web": 1, "api": 0}`</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %} https://sendgrid.com/api/credentials/add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0} {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}


</div>
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %} https://sendgrid.com/api/credentials/add.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=name&password=password&permissions={"email": 0, "web": 1, "api": 0} {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
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
</div>

{% info %} Excluding a permission is the same as granting access rights. In other words, if you do not specify email, web or api at all, the new credentials will have access to all three. If you do not want the credentials to have access to email, web, or api, you *must explicitly set those parameter options to zeroes*. {% endinfo %}


* * * * *

Edit---
layout: page
weight: 0
title: Multiple Credentials
navigation:
  show: true
---
---

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>api_user</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The primary account holder's user ID creating the new account</td>
      </tr>
      <tr>
         <td>api_key</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The primary account holder's password</td>
      </tr>
      <tr>
         <td>username</td>
         <td>Yes</td>
         <td>alphanumeric</td>
         <td>The credential to remove</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs remove %}

<div class="tab-content">
<div class="tab-pane active" id="remove-json">
### Call

{% codeblock %} https://sendgrid.com/api/credentials/remove.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example_user {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "error": "error reason"
}
{% endcodeblock %}


</div>
<div class="tab-pane" id="remove-xml">
### Call

{% codeblock %} https://sendgrid.com/api/credentials/remove.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&username=example_user {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <count>4</count>
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
</div>

