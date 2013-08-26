---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---

Authenticate a customer on your website before displaying their account information so that you can have users manage their SendGrid account on your website completely.

|Parameter|Required|Requirements|
|:---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---
--|:---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---
-|:---
layout: page
weight: 0
title: Authenticate a Customer
navigation:
   show: true
---
-----|
|user|Yes|Customer that is registered under your account.|
|password|Yes|Password the customer submitted.|
|method|Yes|Must be set to *auth*. Allows you to access authentication functionality|

{% xmljsontabs auth %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane" id="auth-xml">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manage.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com&password=theirsubmittedpassword&method=aut {% endcodeblock %}

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
<div markdown="1" class="tab-pane active" id="auth-json">
### Call

{% codeblock %} https://sendgrid.com/apiv2/reseller.manage.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=customer@example.com&password=theirsubmittedpassword&method=aut {% endcodeblock %}

### Response: Success


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

