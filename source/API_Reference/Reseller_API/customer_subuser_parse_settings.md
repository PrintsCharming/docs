---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---

{% anchor h2 %} Get Current Settings {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|
|task|Yes|Must be set to *get*|Retrieve Parse settings|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="get-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&method=parse&task=get&method=parse&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<parse>
   <entry>
      <hostname>www.example.com</hostname>
      <url>www.mydomain.com/parse.php</url>
      <spam_check>1</spam_check>
   </entry>
</parse>

{% endcodeblock %}


### Response: Empty

{% codeblock %} <parse></parse> {% endcodeblock %}

</div>
<div markdown="1" class="tab-pane active" id="get-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=get&method=parse&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:javascript %}
{
  "parse": [
    {
      "hostname": "www.example.com",
      "url": "www.mydomain.com/parse.php",
      "spam_check": 1
    }
  ]
}
{% endcodeblock %}


### Response: Empty

{% codeblock %} "parse":[] {% endcodeblock %}

</div>
</div>

* * * * *


{% anchor h2 %} Create New Entry {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|
|task|Yes|Must be set to *set*|Set Parse settings|
|hostname|Yes|No more than 255 characters|Hostname we will use with your email|
|url|Yes||The parse destination|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="create-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=set&method=parse&user=example@example.com {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="create-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=set&method=parse&user=example@example.com {% endcodeblock %}

### Response


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

* * * * *


{% anchor h2 %} Edit Entry {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|
|task|Yes|Must be set to *update*|Set Parse settings|
|hostname|Yes|No more than 255 characters|Hostname entry you want to update|
|url|Yes||The parse destination|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="edit-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=update&user=example@example.com {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="edit-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&url=www.mydomain.com/parse.php&spam_check=1&method=parse&task=parse&user=example@example.com {% endcodeblock %}

### Response


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

* * * * *


{% anchor h2 %} Delete Entry {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Parse Settingsf
navigation:
   show: true
---
-|
|task|Yes|Must be set to *delete*|Set Parse settings|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|
|hostname|Yes|Must be the hostname you wish to delete.|The host name you will remove for your customer subuser|

{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="delete-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&method=parse&user=example@example.com {% endcodeblock %}

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
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}


</div>
<div markdown="1" class="tab-pane active" id="delete-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&hostname=www.example.com&task=delete&method=parse&user=example@example.com {% endcodeblock %}

### Response


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

