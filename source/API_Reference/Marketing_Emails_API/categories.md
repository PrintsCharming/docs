---
layout: page
weight: 0
title: Categories
navigation:
  show: true
---

This module allows you to create and manage categories within your Marketing Emails.


{% anchor h2 %} create {% endanchor %}


Create a new Category.

|Parameter|Required|Requirements|Description.|
|:--------|:-------|:-----------|:-----------|
|category|Yes|None|The name that will be used for the Category being created.|

{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/create.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY
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
<div markdown="1" class="tab-pane" id="create-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/create.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} add {% endanchor %}


Assign a Category to an existing Marketing Email.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|category|Yes|Must be an existing Category.|The Category that will be added to the marketing email.|
|name|Yes|Must be an existing Marketing Email|The Marketing Email to which the categories will be added.|

{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/add.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY&name=NEWSLETTER
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
<div markdown="1" class="tab-pane" id="add-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/add.xml?&api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY&name=NEWSLETTER

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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} remove {% endanchor %}


Remove specific categories, or all categories from a Marketing Email.\\

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|name|Yes|Must be an existing Marketing Email|The Marketing Email that will have Category(ies) deleted from it.|
|category|No|Must be an existing category currently added to the Marketing Email|Remove the Category with this name. If the category is not specified. all categories will be deleted from the Marketing Email.|

{% xmljsontabs remove %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="remove-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/remove.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY&name=NEWSLETTER
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
<div markdown="1" class="tab-pane" id="remove-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/remove.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&category=CATEGORY&name=NEWSLETTER
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
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

* * * * *


{% anchor h2 %} list {% endanchor %}


List all categories.

|Parameter|Required|Requirements|Description|
|:--------|:-------|:-----------|:----------|
|category|No|Must be an existing Category|Search to see if a specific Category exists rather than a list of all Categories.|

{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/list.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

<h3>Response: Success</h3>

{% codeblock lang:javascript %}
[
  {
    "category": "CATEGORY"
  },
  {
    "category": "CATEGORY2"
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
<div markdown="1" class="tab-pane" id="list-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/list.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<categories>
   <category>
      <category>CATEGORY</category>
   </category>
   <category>
      <category>CATEGORY2</category>
   </category>
</categories>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}




</div>
</div>

