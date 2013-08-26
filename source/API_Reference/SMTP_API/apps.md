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

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'clicktrack':

Rewrites links in e-mail text and html bodies to go through our webservers, allowing for tracking when a link is clicked on.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'subscriptiontrack':

Inserts a subscription management link at the bottom of the text and html bodies. Custom text is set in the settings, with the subscription management link being substituted into the text either as '% %' for plain text bodies, and as a link where the text in between the '%' and '%' is the link text.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'opentrack':

Inserts an `` tag at the bottom of the html section of an e-mail which will be used to track if an e-mail is opened.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'footer':

Inserts a footer at the bottom of the text and HTML bodies.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text/html

</td>
<td markdown="1">
...

</td>
<td markdown="1">
String containing html body

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text/plain

</td>
<td markdown="1">
string

</td>
<td markdown="1">
String containing text body

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'spamcheck':

Tests message with SpamAssassin to determine if it is spam, and drop it if it is.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
<tr markdown="1">
<td markdown="1">
maxscore

</td>
<td markdown="1">
-10.0 to 10.0

</td>
<td markdown="1">
Score after which the message will be dropped (default is 5.0)

</td>
</tr>
<tr markdown="1">
<td markdown="1">
url

</td>
<td markdown="1">
http://www.example.com/spam_post.php

</td>
<td markdown="1">
an optional url to post the email and a copy of the report to

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'ganalytics':

Re-writes links to integrate with Google Analytics.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
<tr markdown="1">
<td markdown="1">
utm_source

</td>
<td markdown="1">
string

</td>
<td markdown="1">
Value for the utm_source field

</td>
</tr>
<tr markdown="1">
<td markdown="1">
utm_medium

</td>
<td markdown="1">
string

</td>
<td markdown="1">
Value for the utm_medium field

</td>
</tr>
<tr markdown="1">
<td markdown="1">
utm_term

</td>
<td markdown="1">
string

</td>
<td markdown="1">
Value for the utm_term field

</td>
</tr>
<tr markdown="1">
<td markdown="1">
utm_content

</td>
<td markdown="1">
string

</td>
<td markdown="1">
Value for the utm_content field

</td>
</tr>
<tr markdown="1">
<td markdown="1">
utm_campaign

</td>
<td markdown="1">
string

</td>
<td markdown="1">
Value for the utm_campaign field

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'domainkeys':

Allows you to specify the domain to use to sign messages with Domain Keys. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on Domain Keys.]({{root_url}}/Apps/domain_keys.html)

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
<tr markdown="1">
<td markdown="1">
domain

</td>
<td markdown="1">
www.example.com

</td>
<td markdown="1">
The domain to sign messages as

</td>
</tr>
<tr markdown="1">
<td markdown="1">
sender

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
1 - Insert a Sender header if the domain specified does not match the From address. 0 - never insert a Sender header

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'dkim':

Allows you to specify the domain to use to sign messages with DKIM certification. This domain should match the domain in the From address of your e-mail. For more info, check out these [details on DKIM.]({{root_url}}/Apps/dkim.html)

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter

</th>
<th markdown="1">
Description

</th>
<th markdown="1">
Example

</th>
</tr>
<tr markdown="1">
<td markdown="1">
domain

</td>
<td markdown="1">
The domain you would like your DKIM certification signed with

</td>
<td markdown="1">
example.com

</td>
</tr>
<tr markdown="1">
<td markdown="1">
use_from

</td>
<td markdown="1">
If enabled, the domain in the From: header of the email will be used to sign your DKIM

</td>
<td markdown="1">
0|1

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'template':

Wraps a template around your email content. Useful for sending out marketing email and other nicely formatted messages.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text/html

</td>
<td markdown="1">
......

</td>
<td markdown="1">
String containing html content for the template (must contain tag)

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'bcc':

Sends a BCC copy of the email created in this transaction to the address specified.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
name@domain.com

</td>
<td markdown="1">
email address destination for the bcc message

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'forwardspam':

Allows for a copy of spam reports to be forwarded to an email address.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
email

</td>
<td markdown="1">
name@domain.com

</td>
<td markdown="1">
email address destination for the bcc message

</td>
</tr>
</tbody>
</table>

* * * * *

### Filter - 'bypass_list_management':

Some emails are too important to do normal list management checks, such as password resets or critical alerts. Enabling this filter will bypass the normal unsubscribe / bounce / spam report checks and queue the e-mail for delivery.

<table markdown="1" class="table table-striped table-bordered">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
Parameter Name

</th>
<th markdown="1">
Parameter Value

</th>
<th markdown="1">
Parameter Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
enable

</td>
<td markdown="1">
0|1

</td>
<td markdown="1">
Disable or enable this App

</td>
</tr>
</tbody>
</table>

