---
layout: page
weight: 0
title: Whitelabel
navigation:
   show: true
---

With the whitelabel API calls you will be able to retrieve whitelabel settings related to your account.

* * * * *


{% anchor h2 %} List {% endanchor %}


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
<td align="left">list</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>list</em></td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>whitelabel</em></td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=whitelabel&task=list
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<whitelabels>
   <whitelabel>
      <mail_domain>email.sendgrid.com</mail_domain>
      <url_domain>email.sendgrid.com</url_domain>
   </whitelabel>
   <whitelabel>
      <mail_domain>email.example.com</mail_domain>
      <url_domain>email.example.com</url_domain>
   </whitelabel>
</whitelabels>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=whitelabel&task=list
{% endcodeblock %}

### Response

{% codeblock lang:javascript %}
[
  {
    "mail_domain": "email.sendgrid.com",
    "url_domain": "email.sendgrid.com"
  },
  {
    "mail_domain": "email.example.com",
    "url_domain": "email.example.com"
  }
]
{% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Append {% endanchor %}


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
<td align="left">list</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>append</em></td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Subuser must be registered under your account</td>
</tr>
<tr class="odd">
<td align="left">mail_domain</td>
<td align="left">Yes</td>
<td align="left">Whitelabel mail_domain used to append a whitelabel record to a subuser</td>
</tr>
<tr class="even">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>whitelabel</em></td>
</tr>
</tbody>
</table>

{% xmljsontabs append %}

<div class="tab-content">
<div class="tab-pane" id="append-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=whitelabel&task=append&user=customer@example.com&mail_domain=email.sendgrid.com=m
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
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="append-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=whitelabel&task=append&user=customer@example.com&mail_domain=email.sendgrid.com
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
</div>

