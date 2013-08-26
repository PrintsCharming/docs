---
layout: page
weight: 0
title: Customer Subuser Automatic Login
navigation:
   show: true
---

Allow customer subusers to manage their account from your website using an iframe to our site.

* * * * *


{% anchor h2 %} Initial API Call {% endanchor %}


In order to login your customer subuser, you need to contact our web API to retrieve the unique URL to automatically login your customer subuser. Then display the generated URL to automatically login yourcustomer subuser.

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
<td align="left">This is the customer subuser you will attempt to automatically login</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">No</td>
<td align="left">Your customer subuser password.</td>
<td align="left">Authenticate the customer subuser with this API call.</td>
</tr>
</tbody>
</table>

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=example@example.com {% endcodeblock %}

### Response

{% codeblock %} params\><params>al_username=username&al_subuser_name=example@example.com&al_hash=b478ab36ebc306990dd283b1c341898e</params></params> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=example@example.com {% endcodeblock %}

### Response

{% codeblock %} "params":"al_username=username&al_subuser_name=example@example.com&al_hash=aa39649af578679d3a90d2cc43245d56" {% endcodeblock %}

* * * * *


{% anchor h2 %} iFrame Usage {% endanchor %}


Using the parameters returned from the Initial API Call, you can construct the iFrame URL as shown below.

{% codeblock %} <iframe src="https://sendgrid.com/account?al_username=username&amp;al_subuser_name=example@example.com&amp;al_hash=aa39649af578679d3a90d2cc43245d56"></iframe> {% endcodeblock %}
