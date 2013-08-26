---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---

{% anchor h2 %} Retrieve Spam Reports {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
-|
|user|Yes|Customer subuser must be registered under your account|The customer subuser we are retrieving spam reports from|
|task|Yes|Must be set to *get*|This will allow you to retrieve the spam reports for the specified user|
|date|No|Must be set to 1|Retrieves the timestamps, it will return a date in a MySQL timestamp format - YYYY-MM-DD HH:MM:SS|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=spamreports&user=example@example.com&task=get&date= {% endcodeblock %}

### Response


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<spamreports>
   <spamreport>
      <email>email1@domain.com</email>
      <created>2009-06-10 12:40:30</created>
   </spamreport>
   <spamreport>
      <email>email2@domain2.com</email>
      <created>2009-06-10 12:40:30</created>
   </spamreport>
</spamreports>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=spamreports&user=example@example.com&task=get&date= {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
[
  {
    "email": "email1@domain.com",
    "created": "2009-06-01 19:41:39"
  },
  {
    "email": "email2@domain2.com",
    "created": "2009-06-01 19:41:39"
  }
]
{% endcodeblock %}


</div>
</div>

* * * * *


{% anchor h2 %} Delete Spam Reports {% endanchor %}


Since SendGrid does not deliver to spam reported addresses, users can remove spam reports from their list at any time if re-delivery to a spam reported address is desired.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Spam Reports
navigation:
   show: true
---
-|
|user|Yes|Customer subuser must be registered under your account|The customer subuser we are retrieving spam reports from|
|task|Yes|Must be set to *delete*|This will allow you to delete a spam report for the specified user|
|email|No|Must be a spam reports|You must specify the spam reports to remove|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=spamreports&user=example@example.com&task=delete&email=spamreport@domain.com {% endcodeblock %}

### Response: Success


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
   <message>Email does not exist</message>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=spamreports&user=example@example.com&task=delete&email=spamreport@domain.com {% endcodeblock %}

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


</div>
</div>

