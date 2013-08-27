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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description.</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>category</td>
         <td>Yes</td>
         <td>None</td>
         <td>The name that will be used for the Category being created.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs create %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="create-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/create.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY
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
https://sendgrid.com/api/newsletter/category/create.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY
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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>category</td>
         <td>Yes</td>
         <td>Must be an existing Category.</td>
         <td>The Category that will be added to the marketing email.</td>
      </tr>
      <tr>
         <td>name</td>
         <td>Yes</td>
         <td>Must be an existing Marketing Email</td>
         <td>The Marketing Email to which the categories will be added.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/add.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY&amp;name=NEWSLETTER
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
https://sendgrid.com/api/newsletter/category/add.xml?&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY&amp;name=NEWSLETTER

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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>name</td>
         <td>Yes</td>
         <td>Must be an existing Marketing Email</td>
         <td>The Marketing Email that will have Category(ies) deleted from it.</td>
      </tr>
      <tr>
         <td>category</td>
         <td>No</td>
         <td>Must be an existing category currently added to the Marketing Email</td>
         <td>Remove the Category with this name. If the category is not specified. all categories will be deleted from the Marketing Email.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs remove %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="remove-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/remove.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY&amp;name=NEWSLETTER
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
https://sendgrid.com/api/newsletter/category/remove.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password&amp;category=CATEGORY&amp;name=NEWSLETTER
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

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>category</td>
         <td>No</td>
         <td>Must be an existing Category</td>
         <td>Search to see if a specific Category exists rather than a list of all Categories.</td>
      </tr>
   </tbody>
</table>


{% xmljsontabs list %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="list-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/category/list.json?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/category/list.xml?api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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

