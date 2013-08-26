---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---

{% anchor h2 %} Retrieve Invalid Emails {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
-|
|user|Yes|Customer subuser must be registered under your account|The customer subuser we are retrieving invalid emails from|
|task|Yes|Must be set to *get*|This will allow you to retrieve the invalid emails for the specified customer subuser|
|date|No|Must be set to 1|Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=get&date= {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<invalidemails>
   <invalidemail>
      <email>isaac@hotmail.comm</email>
      <reason>Mail domain mentioned in email address is unknown</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
   <invalidemail>
      <email>isaac@hotmail</email>
      <reason>Bad Syntax</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
   <invalidemail>
      <email>isaac@example.com</email>
      <reason>Known bad domain</reason>
      <created>2009-06-10 12:40:30</created>
   </invalidemail>
</invalidemails>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=get&date= {% endcodeblock %}

### Response



* * * * *


{% anchor h2 %} Delete Invalid Emails {% endanchor %}


Since SendGrid does not deliver to invalid emails, users can remove invalid emails from their list at any time if re-delivery to a spam reported address is desired.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Invalid Emails
navigation:
   show: true
---
-|
|user|Yes|Customer subuser must be registered under your account|The customer subuser we are retrieving invalid emails from|
|task|Yes|Must be set to *delete*|This will allow you to delete a invalid email for the specified customer subuser|
|email|No|Must be a invalid email|You must specify the invalid emails to remove|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=delete&email=invalidemail@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### Response: Error

{% codeblock %} <result><message>Email does not exist</message></result> {% endcodeblock %}

### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=invalidemails&user=example@example.com&task=delete&email=invalidemail@example.com {% endcodeblock %}

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

