---
layout: page
weight: 0
title: Account Overview
navigation:
   show: true
---

View general account information regarding your customers, including billing cycle, current billing cycle, credit usage, package, overage credits, etc.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|task|Yes|Must be set to *overview*.|The task that allows us to present the customers information.|
|user|Yes|Customer that is registered under your account.|The customer|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.account.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=overview&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <overview>
      <reputation>100</reputation>
      <requests>50000</requests>
      <package>Silver Package</package>
      <credits_allowed>50000</credits_allowed>
      <credits_used>100000</credits_used>
      <credits_remain>0</credits_remain>
      <credits_overage>50000</credits_overage>
      <billing_start_date>2010-08-30</billing_start_date>
      <billing_end_date>2010-09-29</billing_end_date>
      <billing_process_date>2010-09-30</billing_process_date>
   </overview>
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
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/reseller.account.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=overview&user=customer@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "reputation": "100",
  "requests": "500000",
  "package": "Silver Package",
  "credits_allowed": "50000",
  "credits_used": "100000",
  "credits_remain": 0,
  "credits_overage": "50000",
  "billing_start_date": "2010-08-30",
  "billing_end_date": "2010-09-29",
  "billing_process_date": "2010-09-30"
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

