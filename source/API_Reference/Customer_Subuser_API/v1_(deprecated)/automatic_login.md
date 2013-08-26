---
layout: page
weight: 0
title: Automatic Login
navigation:
   show: true
---

<div markdown="1">
Allow subusers to manage their account from your website using an iframe to our site.


{% anchor h2 %} Initial API Call {% endanchor %}
 In order to login your subuser, you need to contact our web API to retrieve the unique URL to automatically login your subuser. Then display the generated URL to automatically login your subuser.

<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Requirements

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set in email format

</td>
<td markdown="1">
This is the subuser you will attempt to automatically login

</td>
</tr>
<tr markdown="1">
<td markdown="1">
password

</td>
<td markdown="1">
No

</td>
<td markdown="1">
Your subuser password.

</td>
<td markdown="1">
Authenticate the subuser with this API call.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs call %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="call-xml">
### Call

{% codeblock %} https://sendgrid.com/api/user.geturl.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<params>
   <params>al_username=username=example@example.com=b478ab36ebc306990dd283b1c341898e</params>
</params>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="call-json">
### Call

{% codeblock %} https://sendgrid.com/api/user.geturl.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=example@example.com {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "params": "al_username=username&al_subuser_name=example@example.com&al_hash=aa39649af578679d3a90d2cc43245d56"
}
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} iFrame Usage {% endanchor %}
 Using the parameters returned from the Initial API Call, you can construct the iFrame URL as shown below. {% codeblock %} iframe src="https://sendgrid.com/account?al_username=username&al_subuser_name=example@example.com&al_hash=aa39649af578679d3a90d2cc43245d56"\></iframe> {% endcodeblock %}

</div>

