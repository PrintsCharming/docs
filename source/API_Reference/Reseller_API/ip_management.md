--- layout: page weight: 0 title: IP Management navigation: show: true
--- {% anchor h2 %} All {% endanchor %}

View all IPs under your account.

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
<td align="left">Must be set to <em>all</em>.</td>
<td align="left">Retrieve all IPs available for your account.</td>
</tr>
<tr class="even">
<td align="left">ip</td>
<td align="left">No</td>
<td align="left">Can be a complete or partial IP address.</td>
<td align="left">Filter your search results.</td>
</tr>
<tr class="odd">
<td align="left">system</td>
<td align="left">No</td>
<td align="left">Must be set to <em>true</em>.</td>
<td align="left">Include IPs assigned by SendGrid.</td>
</tr>
</tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=all
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=all
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.255.250"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.252"
  },
  {
    "ip": "255.255.255.253"
  },
  {
    "ip": "255.255.255.254"
  }
]
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

* * * * *

{% anchor h2 %} Free {% endanchor %}

A listing of all free IPs under your account. A Free IP is any IP that
is not in use by a user or is not linked to an IP grouping.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>free</em>.</td>
<td align="left">Retrieve all free IPs for your account.</td>
</tr>
<tr class="even">
<td align="left">ip</td>
<td align="left">No</td>
<td align="left">Can be a complete or partial IP address.</td>
<td align="left">Filter your search results.</td>
</tr>
</tbody>
</table>

{% xmljsontabs free %}

<div class="tab-content">
<div class="tab-pane" id="free-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=free
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="free-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=free
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.255.250"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.252"
  },
  {
    "ip": "255.255.255.253"
  },
  {
    "ip": "255.255.255.254"
  }
]
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

* * * * *

{% anchor h2 %} Taken {% endanchor %}

A listing of all taken IPs under your account. A Taken IP is any IP that
is in use by a user or is linked to an IP grouping.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>taken</em>.</td>
<td align="left">Retrieve all taken IPs for your account.</td>
</tr>
<tr class="even">
<td align="left">ip</td>
<td align="left">No</td>
<td align="left">Can be a complete or partial IP address.</td>
<td align="left">Filter your search results.</td>
</tr>
</tbody>
</table>

{% xmljsontabs taken %}

<div class="tab-content">
<div class="tab-pane" id="taken-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=taken
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="taken-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=taken
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.255.250"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.252"
  },
  {
    "ip": "255.255.255.253"
  },
  {
    "ip": "255.255.255.254"
  }
]
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

* * * * *

{% anchor h2 %} Available {% endanchor %}

A listing of all available IPs under your account. An Available IP is
any IP that is currently free, or is in use by a user *but* that user is
inactive or that is not linked to an IP grouping.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>available</em>.</td>
<td align="left">Retrieve all available IPs for your account.</td>
</tr>
<tr class="even">
<td align="left">ip</td>
<td align="left">No</td>
<td align="left">Can be a complete or partial IP address.</td>
<td align="left">Filter your search results.</td>
</tr>
</tbody>
</table>

{% xmljsontabs available %}

<div class="tab-content">
<div class="tab-pane" id="available-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=available
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.0</ip>
   <ip>255.255.254.0</ip>
   <ip>255.255.253.0</ip>
   <ip>255.255.252.0</ip>
</ips>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="available-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=available
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.255.250"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.252"
  },
  {
    "ip": "255.255.255.253"
  },
  {
    "ip": "255.255.255.254"
  }
]
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

* * * * *

{% anchor h2 %} Usage {% endanchor %}

The current breakdown of users who are using your IPs.

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Required</th>
<th align="left">Requirements</th>
<th align="left">Parameter</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">task</td>
<td align="left">Yes</td>
<td align="left">Must be set to <em>usage</em>.</td>
<td align="left">Retrieve all IPs in use broken down by user.</td>
</tr>
<tr class="even">
<td align="left">ip</td>
<td align="left">No</td>
<td align="left">Can be a complete or partial IP address.</td>
<td align="left">Filter your search results.</td>
</tr>
<tr class="odd">
<td align="left">user</td>
<td align="left">No</td>
<td align="left">Can be a complete or part of a username.</td>
<td align="left">Filter your search results.</td>
</tr>
<tr class="even">
<td align="left">group</td>
<td align="left">No</td>
<td align="left">Can be a complete or part of a group name.</td>
<td align="left">Filter your search results.</td>
</tr>
<tr class="odd">
<td align="left">system</td>
<td align="left">No</td>
<td align="left">Must be set to <em>true</em>.</td>
<td align="left">Include IPs assigned by SendGrid.</td>
</tr>
</tbody>
</table>

{% xmljsontabs usage %}

<div class="tab-content">
<div class="tab-pane" id="usage-xml">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com
{% endcodeblock %}

### Response

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <entry>
      <ip>255.255.253.0</ip>
      <user>user4@example.com</user>
   </entry>
   <entry>
      <ip>255.255.254.0</ip>
      <user>user4@example.com</user>
   </entry>
</ips>

{% endcodeblock %}

</div>
<div class="tab-pane active" id="usage-json">
### Call

{% codeblock %}
https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com
{% endcodeblock %}

### Response: Success

{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.253.0",
    "user": "user4@example.com"
  },
  {
    "ip": "255.255.254.0",
    "user": "user4@example.com"
  }
]
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

