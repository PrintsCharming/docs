---
layout: page
weight: 0
title: Automatic Login
navigation:
   show: true
---

Allow customers to manage their account from your website using an iframe to our site.

* * * * *


{% anchor h2 %} Initial API Call {% endanchor %}


In order to login your customer, you need to contact our web API to retrieve the unique URL to automatically login your customer. Then display the generated URL to automatically login your customer.

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
<td align="left">Must be set in email format</td>
<td align="left">This is the customer you will attempt to automatically login</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">No</td>
<td align="left">Your customer password.</td>
<td align="left">Authenticate the customer with this API call.</td>
</tr>
<tr class="odd">
<td align="left">method</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>geturl</em></td>
<td align="left">Allows you to access automatic login functionality</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=customer@example.com {% endcodeblock %}

### Response

{% codeblock %} params\><params>al_username=username&al_subuser_name=customer@example.com&al_hash=b478ab36ebc306990dd283b1c341898e</params></params>JSON Call

</h3>
{% codeblock %} https://sendgrid.com/api/distributor.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=customer@example.com {% endcodeblock %}

### Response

{% codeblock %} "params":"al_username=username&al_subuser_name=customer@example.com&al_hash=aa39649af578679d3a90d2cc43245d56" {% endcodeblock %}

* * * * *


{% anchor h2 %} iFrame Usage {% endanchor %}


Using the parameters returned from the Initial API Call, you can construct the iFrame URL as shown below.

{% codeblock %} iframe src="https://sendgrid.com/account?al_username=username&al_subuser_name=example@example.com&al_hash=aa39649af578679d3a90d2cc43245d56"\></iframe>
