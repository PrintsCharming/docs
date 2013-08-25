--- layout: page weight: 0 title: Account Overview navigation: show:
true ---

View general account information regarding your customers, including
billing cycle, current billing cycle, credit usage, package, overage
credits, etc.

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
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>overview</em>.</td>
<td align="left">The task that allows us to present the customers information.</td>
</tr>
<tr class="even">
<td align="left">user</td>
<td align="left">Yes</td>
<td align="left">Customer that is registered under your account.</td>
<td align="left">The customer</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.account.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=overview&user=customer@example.com
{% endcodeblock %}

### Response: Success

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
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.account.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=overview&user=customer@example.com
{% endcodeblock %}

### Response: Success

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

