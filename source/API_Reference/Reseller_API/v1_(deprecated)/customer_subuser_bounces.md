---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---

{% anchor h2 %} Retrieve Bounces {% endanchor %}


Note that you can use *either* the days parameter *or* the start_date and end_date parameter.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
-|
|user|Yes|Customer subuser must be registered under your account|The customer subuser we are retrieving bounces from|
|task|Yes|Must be set to *get*|This will allow you to retrieve the bounces for the specified customer subuser|
|date|No|Must be set to 1|Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=get&date= {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<bounces>
   <bounce>
      <email>email1@domain.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email1@domain.com</reason>
      <created>2009-06-10 12:40:30</created>
   </bounce>
   <bounce>
      <email>email2@domain2.com</email>
      <status>5.1.1</status>
      <reason>host [127.0.0.1] said: 550 5.1.1 unknown or illegal user: email2@domain2.com</reason>
      <created>2009-06-10 12:40:30</created>
   </bounce>
</bounces>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=get&date= {% endcodeblock %}

### Response



* * * * *


{% anchor h2 %} Delete Bounces {% endanchor %}


Since SendGrid does not re-deliver to bounced addresses, users can remove bounces from their list at any time if redelivery to a bounced address is desired.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
---
layout: page
weight: 0
title: Customer Subuser Bounces
navigation: Event Notification URL
show: true
---
-|
|user|Yes|Subuser must be registered under your account|The subuser we are retrieving bounces from|
|task|Yes|Must be set to *delete*|This will allow you to delete the bounces for the specified user|
|email|No|Bounce email address you want to delete|You must specify the bounced email message to remove|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=delete&email=bounce@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error

{% codeblock %} result\><message>Email does not exist</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=bounces&user=example@example.com&task=delete&email=bounce@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


### Response: Error


{% codeblock lang:javascript %}
{
  "message": "Email does not exist"
}
{% endcodeblock %}

