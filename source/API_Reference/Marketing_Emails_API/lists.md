--- layout: page weight: 0 title: Lists navigation: show: true ---

This endpoint allows you to manage and create Recipient Lists associated
with the Marketing Email feature.

{% anchor h2 %} add {% endanchor %}

Create a new Recipient List.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>list</td>
         <td>Yes</td>
         <td>None</td>
         <td>Create a Recipient List with this name.</td>
      </tr>
      <tr>
         <td>name</td>
         <td>No</td>
         <td>None</td>
         <td>Specify the column name for the 'name' associated with email addresses.</td>
      </tr>
      <tr>
         <td>*columnname*</td>
         <td>No</td>
         <td>None</td>
         <td>Specify additional column names. The format needs to be    =columnname[*columnname*] will be the replacement tag.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs add %}

<div class="tab-content">
<div class="tab-pane active" id="add-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/add.json?list=test789&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
<div class="tab-pane" id="add-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/add.xml?list=test789&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
   <message>error: reason</message>
</result>

{% endcodeblock %}
</result>

</div>
</div>

* * * * *

{% anchor h2 %} edit {% endanchor %}

Rename a Recipient List.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>list</td>
         <td>Yes</td>
         <td>Must be an existing Recipient List.</td>
         <td>This is the name of the Recipient List to be renamed.</td>
      </tr>
      <tr>
         <td>newlist</td>
         <td>Yes</td>
         <td>None</td>
         <td>Specify the new name for the Recipient List.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs edit %}

<div class="tab-content">
<div class="tab-pane active" id="edit-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/edit.json?list=test7890&newlist=test567&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
<div class="tab-pane" id="edit-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/edit.xml?list=test7890&newlist=test567&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
   <message>error: reason</message>
</result>

{% endcodeblock %}
</result>

</div>
</div>

* * * * *

{% anchor h2 %} get {% endanchor %}

List all Recipient Lists on your account, or check if a particular List
exists.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>list</td>
         <td>No</td>
         <td>None</td>
         <td>Check for this particular list. (To list all Recipient Lists on youraccount exclude this parameter)</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs get %}

<div class="tab-content">
<div class="tab-pane active" id="get-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/get.json?list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

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
<div class="tab-pane" id="get-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/get.xml?list=test&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

### Response: Success

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

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>list</td>
         <td>Yes</td>
         <td>Must be an existing Recipient List.</td>
         <td>Remove this Recipient List.</td>
      </tr>
   </tbody>
</table>

{% xmljsontabs delete %}

<div class="tab-content">
<div class="tab-pane active" id="delete-json">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/delete.json?list=test5678&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
<div class="tab-pane" id="delete-xml">
### Call

{% codeblock %}
https://sendgrid.com/api/newsletter/lists/delete.xml?list=test5678&api_user=your_sendgrid_username&api_key=your_sendgrid_password
{% endcodeblock %}

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
   <message>error: reason</message>
</result>

{% endcodeblock %}
</result>

</div>
</div>

