---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---

List

Obtain a complete list of all IP's and which are free, taken or available.

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
</tr>
<tr markdown="1">
<td markdown="1">
list

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to either ( all / free / taken / available )

</td>
</tr>
</tbody>
</table>
Here is a brief explanation of each option available for the list parameter:

all
:   All IP addresses available to reseller, regardless of whether or not the IP is taken by a subuser
free
:   All free IP addresses for the reseller. If a subuser is using an IP, it will not show up on this list
taken
:   All taken IP addresses for the reseller. Only IP addresses that taken by subusers will show up on this list
available
:   All available IP addresses for the reseller including all free IP addresses. If a subuser is deactivated*and* is assigned an IP, that IP will show up on this list since that IP address is not being used by anyone

{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
	https://sendgrid.com/apiv2/customer.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=all
	{% endcodeblock %}
	<h3>Response</h3>
	
{% codeblock lang:javascript %}
[
  {
    "ip": "255.255.255.250"
  },
  {
    "ip": "255.255.255.251"
  },
  {
    "ip": "255.255.255.252"
  }
]
{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&list=all
{% endcodeblock %}
<h3>Response</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<ips>
   <ip>255.255.255.250</ip>
   <ip>255.255.255.251</ip>
   <ip>255.255.255.252</ip>
</ips>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Subuser IP Usage {% endanchor %}
 If your account has more than one IP address, you can manage what IPs your subusers are allowed to send from. If you remove all IPs from a specified user, they will use all IPs from from your list.

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
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *list*

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
</tr>
</tbody>
</table>
{% xmljsontabs usage %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="usage-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.sendip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<sendips>
   <ocluster>o1.sendgrid.net</ocluster>
   <ips>
      <ip>255.255.255.250</ip>
      <ip>255.255.255.251</ip>
      <ip>255.255.255.252</ip>
      <ip>255.255.255.253</ip>
      <ip>255.255.255.254</ip>
   </ips>
</sendips>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>User does not exist</message>
</result>

{% endcodeblock %}




</div>
<div markdown="1" class="tab-pane active" id="usage-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.sendip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=list&user=example@example.com
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
{
  "success": "success",
  "outboundcluster": "o1.sendgrid.net",
  "ips": [
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
}
{% endcodeblock %}




### Response: Error




{% codeblock lang:javascript %}
{
  "error": {
    "code": 400,
    "message": "User does not exist"
  }
}
{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} Subuser IP Assignment {% endanchor %}
 You need to assign at least ONE IP to your subuser.

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
</tr>
<tr markdown="1">
<td markdown="1">
task

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be set to *append*

</td>
</tr>
<tr markdown="1">
<td markdown="1">
user

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Subuser must be registered under your account

</td>
</tr>
<tr markdown="1">
<td markdown="1">
set

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
Must be either: **none**: Remove all ips. **all**: Apply all possible ips to subuser. **specify**: Specify the ips to the subser. Must be a valid set of IPs (use the list call to determine valid IPs)

</td>
</tr>
<tr markdown="1">
<td markdown="1">
ip[]

</td>
<td markdown="1">
No

</td>
<td markdown="1">
If the *set* parameter is set, then you must specify the IPs. Use the ip[] parameter to specify an IP. [ IE - ip[]=255.255.255.0&ip[]=255.255.255.1 ]

</td>
</tr>
</tbody>
</table>
{% xmljsontabs subuser %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="subuser-xml">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.sendip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&set=specify&user=example@example.com&ip[]=255.255.255.250&ip[]=255.255.255.255
{% endcodeblock %}
<h3>Response: Success</h3>

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
<div markdown="1" class="tab-pane active" id="subuser-json">
### Call



{% codeblock %}
https://sendgrid.com/apiv2/customer.sendip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=append&set=specify&user=example@example.com&ip[]=255.255.255.250&ip[]=255.255.255.255
{% endcodeblock %}
<h3>Response: Success</h3>

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
