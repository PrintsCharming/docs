---
layout: page
weight: 0
title: Lists
navigation:
  show: true
---

This endpoint allows you to manage and create Recipient Lists associated with the Marketing Email feature.


{% anchor h2 %} add {% endanchor %}


Create a new Recipient List.

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
<th markdown="1">
Description

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
None

</td>
<td markdown="1">
Create a Recipient List with this name.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
name

</td>
<td markdown="1">
No

</td>
<td markdown="1">
None

</td>
<td markdown="1">
Specify the column name for the 'name' associated with email addresses.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
*columnname*

</td>
<td markdown="1">
No

</td>
<td markdown="1">
None

</td>
<td markdown="1">
Specify additional column names. The format needs to be

    &columnname=columnname

[*columnname*] will be the replacement tag.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs add %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="add-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/add.json?list=test789&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
https://sendgrid.com/api/newsletter/lists/add.xml?list=test789&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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


 </result>

</div>
</div>

* * * * *


{% anchor h2 %} edit {% endanchor %}


Rename a Recipient List.

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
<th markdown="1">
Description

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
Must be an existing Recipient List.

</td>
<td markdown="1">
This is the name of the Recipient List to be renamed.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
newlist

</td>
<td markdown="1">
Yes

</td>
<td markdown="1">
None

</td>
<td markdown="1">
Specify the new name for the Recipient List.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs edit %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="edit-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/edit.json?list=test7890&amp;newlist=test567&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane" id="edit-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/edit.xml?list=test7890&amp;newlist=test567&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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


 </result>

</div>
</div>

* * * * *


{% anchor h2 %} get {% endanchor %}


List all Recipient Lists on your account, or check if a particular List exists.

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
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
list

</td>
<td markdown="1">
No

</td>
<td markdown="1">
None

</td>
<td markdown="1">
Check for this particular list. (To list all Recipient Lists on your account exclude this parameter)

</td>
</tr>
</tbody>
</table>
{% xmljsontabs get %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="get-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/get.json?list=test&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:javascript %}
[
  {
    "list": "test"
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
<div markdown="1" class="tab-pane" id="get-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/get.xml?list=test&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
{% endcodeblock %}
<h3>Response: Success</h3>

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<lists>
   <list>
      <list>test</list>
   </list>
</lists>

{% endcodeblock %}




### Response: Error




{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error: reason</message>
</result>

{% endcodeblock %}


 </result>

</div>
</div>

* * * * *


{% anchor h2 %} delete {% endanchor %}


Remove a Recipient List from your account.

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
<th markdown="1">
Description

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
Must be an existing Recipient List.

</td>
<td markdown="1">
Remove this Recipient List.

</td>
</tr>
</tbody>
</table>
{% xmljsontabs delete %}

<div markdown="1" class="tab-content">
<div markdown="1" class="tab-pane active" id="delete-json">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/delete.json?list=test5678&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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
<div markdown="1" class="tab-pane" id="delete-xml">
### Call



{% codeblock %}
https://sendgrid.com/api/newsletter/lists/delete.xml?list=test5678&amp;api_user=your_sendgrid_username&amp;api_key=your_sendgrid_password
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


 </result>

</div>
</div>

