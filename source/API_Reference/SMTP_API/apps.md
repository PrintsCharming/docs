---
layout: page
weight: 0
title: Apps (Filters)
navigation:
  show: true
---

Following are the apps that can be specified in the filters section of the X-SMTPAPI header. All filters and setting names must be lowercase.

Please note that if a filter is not specified as being either disabled or enabled in the X-SMTPAPI header, it will default to the state of the app in the "Apps" tab on the website.


{% warning %} If you're enabling an App, also called a filter, via SMTPAPI, you are required to define all the parameters for the App. If you have the App disabled on the web interface, our system will not pull the settings for the disabled app when you dynamically enable it. For instance, if you have a template designed but disabled, you can't just enable it via the API; you need to define the template in the API call itself. {% endwarning %}


For more information on the utility of these apps, please check out the [Apps]({{root_url}}/Apps/) section.

### Filter - 'gravatar':

Inserts an img tag at the bottom of the html section of an e-mail to display the gravatar associated with the mail sender.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'clicktrack':

Rewrites links in e-mail text and html bodies to go through our webservers, allowing for tracking when a link is clicked on.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'subscriptiontrack':

Inserts a subscription management link at the bottom of the text and html bodies. Custom text is set in the settings, with the subscription management link being substituted into the text either as '% %' for plain text bodies, and as a link where the text in between the '%' and '%' is the link text.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'opentrack':

Inserts an `` tag at the bottom of the html section of an e-mail which will be used to track if an e-mail is opened.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'footer':

Inserts a footer at the bottom of the text and HTML bodies.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
<tr>
<td>
text/html

</td>
<td>
...

</td>
<td>
String containing html body

</td>
</tr>
<tr>
<td>
text/plain

</td>
<td>
string

</td>
<td>
String containing text body

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'spamcheck':

Tests message with SpamAssassin to determine if it is spam, and drop it if it is.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
<tr>
<td>
maxscore

</td>
<td>
-10.0 to 10.0

</td>
<td>
Score after which the message will be dropped (default is 5.0)

</td>
</tr>
<tr>
<td>
url

</td>
<td>
http://www.example.com/spam\_post.php

</td>
<td>
an optional url to post the email and a copy of the report to

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'ganalytics':

Re-writes links to integrate with Google Analytics.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
<tr>
<td>
utm\_source

</td>
<td>
string

</td>
<td>
Value for the utm\_source field

</td>
</tr>
<tr>
<td>
utm\_medium

</td>
<td>
string

</td>
<td>
Value for the utm\_medium field

</td>
</tr>
<tr>
<td>
utm\_term

</td>
<td>
string

</td>
<td>
Value for the utm\_term field

</td>
</tr>
<tr>
<td>
utm\_content

</td>
<td>
string

</td>
<td>
Value for the utm\_content field

</td>
</tr>
<tr>
<td>
utm\_campaign

</td>
<td>
string

</td>
<td>
Value for the utm\_campaign field

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'domainkeys':

Allows you to specify the domain to use to sign messages with Domain Keys. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on Domain Keys.]({{root_url}}/Apps/domain_keys.html)

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
<tr>
<td>
domain

</td>
<td>
www.example.com

</td>
<td>
The domain to sign messages as

</td>
</tr>
<tr>
<td>
sender

</td>
<td>
0|1

</td>
<td>
1 - Insert a Sender header if the domain specified does not match the From address. 0 - never insert a Sender header

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'dkim':

Allows you to specify the domain to use to sign messages with DKIM certification. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on DKIM.]({{root_url}}/Apps/dkim.html)

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter

</th>
<th>
Description

</th>
<th>
Example

</th>
</tr>
<tr>
<td>
domain

</td>
<td>
The domain you would like your DKIM certification signed with

</td>
<td>
example.com

</td>
</tr>
<tr>
<td>
use\_from

</td>
<td>
If enabled, the domain in the From: header of the email will be used to sign your DKIM

</td>
<td>
0|1

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'template':

Wraps a template around your email content. Useful for sending out marketing email and other nicely formatted messages.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
<tr>
<td>
text/html

</td>
<td>
......

</td>
<td>
String containing html content for the template (must contain tag)

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'bcc':

Sends a BCC copy of the email created in this transaction to the address specified.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
email

</td>
<td>
name@domain.com

</td>
<td>
email address destination for the bcc message

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'forwardspam':

Allows for a copy of spam reports to be forwarded to an email address.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
email

</td>
<td>
name@domain.com

</td>
<td>
email address destination for the bcc message

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'bypass\_list\_management':

Some emails are too important to do normal list management checks, such as password resets or critical alerts. Enabling this filter will bypass the normal unsubscribe / bounce / spam report checks and queue the e-mail for delivery.

<table class="table table-striped table-bordered">
<tbody>
<tr>
<th>
Parameter Name

</th>
<th>
Parameter Value

</th>
<th>
Parameter Description

</th>
</tr>
<tr>
<td>
enable

</td>
<td>
0|1

</td>
<td>
Disable or enable this App

</td>
</tr>
</tbody>
</table>

