--- layout: page weight: 0 title: Multiple Credentials navigation: show:
true --- {% anchor h2 %} Add user credential {% endanchor %}

Notes: This API call allows SendGrid resellers to add a new set of
credentials to a specified child account.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>The username must be be between 3 and 64 characters and cannot becompletely numeric.</td>
         <td>The child account we are adding a credential to.</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>The task must be set to 'add'.</td>
         <td>The task we are setting so we create a credential.</td>
      </tr>
      <tr>
         <td>credential\_name</td>
         <td>Yes</td>
         <td>The credential\_name must be be between 3 and 64 characters and cannotbe completely numeric.</td>
         <td>The credential we are creating under the child account.</td>
      </tr>
      <tr>
         <td>credential\_password</td>
         <td>Yes</td>
         <td>Must be at least 6 characters.</td>
         <td>The password used to authenticate the newly generated credential.</td>
      </tr>
   </tbody>
</table>

### XML API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=add&credential_name=reseller_customer_credential&credential_password=reseller_customer_password
{% endcodeblock %}

#### Return - Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

#### Return - Error

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

### JSON API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=add&credential_name=reseller_customer_credential&credential_password=reseller_customer_password
{% endcodeblock %}

#### Return - Success

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

#### Return - Error

{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

* * * * *

{% anchor h2 %} Edit user credential {% endanchor %}

Notes: This API call allows SendGrid resellers to edit an already
existing credential password. Changing the credential name is not
currently allowed.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>The username must be be between 3 and 64 characters and cannot becompletely numeric.</td>
         <td>The username that we are checking against existing usernames.</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>The task must be set to 'edit'.</td>
         <td>The task we are setting so we edit a credential password</td>
      </tr>
      <tr>
         <td>credential\_name</td>
         <td>Yes</td>
         <td>The credential\_name must be be between 3 and 64 characters and cannotbe completely numeric.</td>
         <td>The credential we want to modify</td>
      </tr>
      <tr>
         <td>new\_credential\_password</td>
         <td>Yes</td>
         <td>Must be at least 6 characters</td>
         <td>The updated password</td>
      </tr>
   </tbody>
</table>

### XML API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=edit&credential_name=reseller_customer_credential&new_credential_password=reseller_customer_password
{% endcodeblock %}

#### Return - Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

#### Return - Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=edit&credential_name=reseller_customer_credential&new_credential_password=reseller_customer_password
{% endcodeblock %}

#### Return - Success

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

#### Return - Error

{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

</h4>
{% anchor h2 %} Delete user credential {% endanchor %}

Notes: This API call allows SendGrid resellers to delete an existing
credential under a child account.

<table class="table table-bordered table-striped">
   <tbody>
      <tr>
         <th>Parameter</th>
         <th>Required</th>
         <th>Requirements</th>
         <th>Description</th>
      </tr>
      <tr>
         <td>user</td>
         <td>Yes</td>
         <td>The username must be be between 3 and 64 characters and cannot becompletely numeric.</td>
         <td>The username that we are checking against existing usernames.</td>
      </tr>
      <tr>
         <td>task</td>
         <td>Yes</td>
         <td>The task must be set to 'delete'.</td>
         <td>The task we are setting so we delete a credential</td>
      </tr>
      <tr>
         <td>credential\_name</td>
         <td>Yes</td>
         <td>The credential\_name must be be between 3 and 64 characters and cannotbe completely numeric.</td>
         <td>The credential we want to remove</td>
      </tr>
   </tbody>
</table>

### XML API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.xml?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=delete&credential_name=reseller_customer_credential
{% endcodeblock %}

#### Return - Success

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>success</message>
</result>

{% endcodeblock %}

#### Return - Error

{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages
...</error>
      ...
   </errors>
</result>

{% endcodeblock %}

### JSON API Request

{% codeblock %}
https://sendgrid.com/apiv2/reseller.credential.json?api_user=your_sendgrid_username&api_key=your_sendgrid_password&user=reseller_customer&task=delete&credential_name=reseller_customer_credential
{% endcodeblock %}

#### Return - Success

{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

#### Return - Error

{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}
