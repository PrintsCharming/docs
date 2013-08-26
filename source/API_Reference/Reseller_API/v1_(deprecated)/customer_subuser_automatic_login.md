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

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|user|Yes|Must be set in email format|This is the customer subuser you will attempt to automatically login|
|password|No|Your customer subuser password.|Authenticate the customer subuser with this API call.|

### XML Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>
{% codeblock %}
<params><params>al_username=username&al_subuser_name=example@example.com&al_hash=b478ab36ebc306990dd283b1c341898e</params></params>
{% endcodeblock %}



### JSON Call



{% codeblock %}
https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=geturl&user=example@example.com
{% endcodeblock %}
<h3>Response</h3>
{% codeblock %}
{"params":"al_username=username&al_subuser_name=example@example.com&al_hash=aa39649af578679d3a90d2cc43245d56"}
{% endcodeblock %}



* * * * *


{% anchor h2 %} iFrame Usage {% endanchor %}


Using the parameters returned from the Initial API Call, you can construct the iFrame URL as shown below.

{% codeblock %} <iframe src="https://sendgrid.com/account?al_username=username&amp;al_subuser_name=example@example.com&amp;al_hash=aa39649af578679d3a90d2cc43245d56"></iframe> {% endcodeblock %}
