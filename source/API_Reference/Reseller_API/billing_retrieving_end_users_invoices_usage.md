---
layout: page
weight: 0
title: Retrieving Invoice Usage
navigation:
   show: true
---

Retrieve invoices/usages from customers.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>usage</em>.</td>
</tr>
<tr class="even">
<td align="left">number</td>
<td align="left">Yes</td>
<td align="left">Must be the invoice number you received from SendGrid.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.billing.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&number=2010010001&task=usag {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<usage>
   <number>2010010001</number>
   <invoices>
      <invoice>
         <number>201001000100</number>
         <credits>123456</credits>
         <date_invoiced>2010-09-01 00:00:00</date_invoiced>
         <status>Unpaid</status>
         <amount>1001</amount>
         <overage>6.95</overage>
         <type>Recurring Bill</type>
         <prorated>0</prorated>
         <start_date>2010-08-01</start_date>
         <end_date>2010-08-31</end_date>
         <username>user4@example.com</username>
         <package>Example Package</package>
         <additional_charges>0</additional_charges>
         <final_amount>1007.95</final_amount>
      </invoice>
      <invoice>
         <number>201001000200</number>
         <credits>1333</credits>
         <date_invoiced>2010-09-05 00:00:00</date_invoiced>
         <status>Unpaid</status>
         <amount>13.95</amount>
         <overage>0</overage>
         <type>Recurring Bill</type>
         <prorated>0</prorated>
         <start_date>2010-08-01</start_date>
         <end_date>2010-08-31</end_date>
         <username>user5@example.com</username>
         <package>Example Package</package>
         <additional_charges>0</additional_charges>
         <final_amount>13.95</final_amount>
      </invoice>
   </invoices>
</usage>

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
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.billing.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&number=2010010001&task=usag {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "number": "2010010001",
  "invoices": [
    {
      "number": "201001000100",
      "credits": 123456,
      "date_invoiced": "2010-09-0100:00:00",
      "status": "Unpaid",
      "amount": 1001,
      "overage": 6.95,
      "type": "Recurring Bill",
      "prorated": 0,
      "start_date": "2010-08-01",
      "end_date": "2010-08-31",
      "username": "user4@example.com",
      "package": "Example Package",
      "additional_charges": 0,
      "final_amount": 1007.95
    },
    {
      "number": "201001000200",
      "credits": "1333",
      "date_invoiced": "2010-09-05 00:00:00",
      "status": "Unpaid",
      "amount": 13.95,
      "overage": 0,
      "type": "Recurring Bill",
      "prorated": 0,
      "start_date": "2010-08-01",
      "end_date": "2010-08-31",
      "username": "user5@example.com",
      "package": "Example Package",
      "additional_charges": 0,
      "final_amount": 13.95
    }
  ]
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

