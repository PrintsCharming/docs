---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---

{% anchor h2 %} List {% endanchor %}


List all of the available apps.

Note: The *name* entry is used in all the other API calls to identify a app.

|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|
|task|Yes|Must be set to *getavailable*|Retrieve Available Apps|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filters>
   <filter>
      <name>twitter</name>
      <title markdown="1">
Twitter

</title>
      <description>This plugin allows you to send an email message to twitter</description>
      <activated>0</activated>
   </filter>
   ...
</filters>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&task=getavailable&method=apps&user=example@example.com {% endcodeblock %}

### Response: Success



* * * * *


{% anchor h2 %} Activate App {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|
|task|Yes|Must be set to *activate*|Retrieve Available Apps|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=activate&user=example@example.com {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Deactivate App {% endanchor %}


|Parameter|Required|Requirements|Description|
|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
---
layout: page
weight: 0
title: Customer Subuser Apps
navigation:
   show: true
---
-|
|task|Yes|Must be set to *deactivate*|Retrieve Available Apps|
|user|Yes|Customer subuser must be registered under your account|The customer subuser who we will update|

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=deactivate&user=example@example.com {% endcodeblock %}

### Response


{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Customize App {% endanchor %}


These API calls require that settings are passed using POST.

### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=example@example.com {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field_value</field_name>
   ...
</filter>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages ...</message>
</result>

{% endcodeblock %}


#### Return - Empty

This is returned if that filter has no settings or is not enabled.


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&method=apps&task=setup&user=example@example.com {% endcodeblock %}

### Response: Success



#### Return - Empty

This is returned if that filter has no settings or is not enabled.


{% codeblock lang:javascript %}
{
  "settings": null
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Get Current Settings {% endanchor %}


### XML Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com&method=app {% endcodeblock %}

### Response: Success


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter>
   <field_name>field_value</field_name>
   ...
</filter>

{% endcodeblock %}


### Response: Error


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <message>... error messages ...</message>
</result>

{% endcodeblock %}


#### Return - Empty

This is returned if that filter has no settings or is not enabled.


{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<filter/>

{% endcodeblock %}


### JSON Call

{% codeblock %} https://sendgrid.com/api/distributor.manageSubuser.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&name=twitter&task=getsettings&user=example@example.com&method=app {% endcodeblock %}

### Response: Success



### Response: Error


{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


#### Return - Empty

This is returned if that filter has no settings or is not enabled.

{% codeblock %} {"settings":null} {% endcodeblock %}
