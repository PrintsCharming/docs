---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---

{% anchor h2 %} All {% endanchor %}


View all IPs under your account.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
-|
|task|Yes|Must be set to *all*.|Retrieve all IPs available for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|
|system|No|Must be set to *true*.|Include IPs assigned by SendGrid.|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=all {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=all {% endcodeblock %}

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


A listing of all free IPs under your account. A Free IP is any IP that is not in use by a user or is not linked to an IP grouping.

|Parameter|Required|Requirements|Parameter|
|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|
|task|Yes|Must be set to *taken*.|Retrieve all taken IPs for your account.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|

{% xmljsontabs taken %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="taken-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=taken {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="taken-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=taken {% endcodeblock %}

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


A listing of all available IPs under your account. An Available IP is any IP that is currently free, or is in use by a user *but* that user is inactive or that is not linked to an IP grouping.

|Parameter|Required|Requirements|Parameter|
|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: IP Management
navigation:
   show: true
---
--|
|task|Yes|Must be set to *usage*.|Retrieve all IPs in use broken down by user.|
|ip|No|Can be a complete or partial IP address.|Filter your search results.|
|user|No|Can be a complete or part of a username.|Filter your search results.|
|group|No|Can be a complete or part of a group name.|Filter your search results.|
|system|No|Must be set to *true*.|Include IPs assigned by SendGrid.|

{% xmljsontabs usage %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="usage-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="usage-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.ip.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=usage&user=example.com {% endcodeblock %}

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

