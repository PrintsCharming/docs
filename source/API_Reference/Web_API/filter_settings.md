---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---

For a more detailed description of each of the Apps below, please visit the [Apps]({{root_url}}/Apps) page.


{% anchor h2 %} Address Whitelist {% endanchor %}
 [API App Name: "addresswhitelist"] 
{% info %} When using this call, you must define all emails & domains here. Using this call will overwrite any current settings for this filter. This would also be how you remove an entry, by excluding if from the call. {% endinfo %}


|Parameter|Description|Example|
|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
|
|bcc|An email address to be the BCC recipient.|email@example.com|

* * * * *


{% anchor h2 %} Click Tracking {% endanchor %}
 [API app name: "clicktrack"]

|Parameter|Description|Example|
|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
|
|domain|The domain to sign messages as|example.com|
|sender|1 to insert a sender header if the domain specified does not match the from address 0 to never insert a Sender header|0|1|

* * * * *


{% anchor h2 %} DKIM {% endanchor %}
 [API app name:"dkim"]

<table markdown="1" class="table table-bordered table-striped">
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
</table>

* * * * *


{% anchor h2 %} Email Templates {% endanchor %}
 [API app name:"template"]

<table markdown="1" class="table table-bordered table-striped">
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
<td markdown="1">
text_html

</td>
<td markdown="1">
A string that holds the template html body

</td>
<td markdown="1">
Content

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} Event Notification {% endanchor %}
 [API app name:"eventnotify"] 
{% info %} All fields are required for each call. {% endinfo %}


|Parameter|Description|Example|
|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
-|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
|
|utm_source|Name of the referrer source|Google, SomeDomain.com, or Marketing EmailA|
|utm_medium|Name of the marketing medium|Email, Affiliate, or MobileApp|
|utm_campaign|Name of the campaign|Quarter1, FallShoeSale|
|utm_term|Identify paid keywords|Poultry, Health|
|utm_content|Use to differentiate ads|PageA, PageB|

* * * * *


{% anchor h2 %} Gravatar {% endanchor %}
 [API app name:"gravatar"]

<table markdown="1" class="table table-bordered table-striped">
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
None

</td>
<td markdown="1">
N/A

</td>
<td markdown="1">
N/A

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} Open Tracking {% endanchor %}
 [API app name:"opentrack"]

<table markdown="1" class="table table-bordered table-striped">
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
None

</td>
<td markdown="1">
N/A

</td>
<td markdown="1">
N/A

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} Return Path Seedlist {% endanchor %}
 [API app name:"seedlist"]

<table markdown="1" class="table table-bordered table-striped">
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
seedlist_option

</td>
<td markdown="1">
</td>
<td markdown="1">
</td>
</tr>
</tr>
<td markdown="1">
frequency

</td>
<td markdown="1">
The number of times per day the Seedlist should be used

</td>
<td markdown="1">
</td>
</tr>
<tr markdown="1">
<td markdown="1">
keyword_frequency

</td>
<td markdown="1">
</td>
<td markdown="1">
</td>
</tr>
<tr markdown="1">
<td markdown="1">
keywords

</td>
<td markdown="1">
</td>
<td markdown="1">
</td>
</tr>
<tr markdown="1">
<td markdown="1">
type

</td>
<td markdown="1">
</td>
<td markdown="1">
</td>
</tr>
<tr markdown="1">
<td markdown="1">
list

</td>
<td markdown="1">
The addresses in the Seedlist

</td>
<td markdown="1">
www.example.com/mylist.csv

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} SPAM Filter Checker {% endanchor %}
 [API app name:"spamcheck"]

<table markdown="1" class="table table-bordered table-striped">
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
maxscore

</td>
<td markdown="1">
Emails with a spam score over this value will be considered spam and will not be delivered to the recipient. The default spam threshold is 5.0, but you can set this to any value you wish. We use SpamAssassin to process the spam checks for this filter, so you can base your maxscore setting on values typically used with SpamAssassin

</td>
<td markdown="1">
1.2

</td>
</tr>
<tr markdown="1">
<td markdown="1">
url

</td>
<td markdown="1">
URL to post the email and a copy of the detailed SpamAssassin report describing why the email was designated as spam

</td>
<td markdown="1">
www.example.com/spamcheck.php

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} Subscription Tracking {% endanchor %}
 [API app name:"subscriptiontrack"]

<table markdown="1" class="table table-bordered table-striped">
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
text/html

</td>
<td markdown="1">
String for the HTML e-mail body

</td>
<td markdown="1">
If you would like to unsubscribe and stop receiving these emails &lt;% click here %&gt;

</td>
</tr>
<tr markdown="1">
<td markdown="1">
text/plain

</td>
<td markdown="1">
String for the plain text e-mail body

</td>
<td markdown="1">
If you would like to unsubscribe and stop receiving these emails click here: \<% %\>.

</td>
</tr>
<tr markdown="1">
<td markdown="1">
url

</td>
<td markdown="1">
a URL the customer will be redirected to on clicking the subscription management link

</td>
<td markdown="1">
www.example.com/UnsubscribeLandingPage

</td>
</tr>
<tr markdown="1">
<td markdown="1">
landing

</td>
<td markdown="1">
HTML content for a landing page that will be displayed by SendGrid

</td>
<td markdown="1">
Content

</td>
</tr>
<tr markdown="1">
<td markdown="1">
replace

</td>
<td markdown="1">
a tag that can be added to the content that will be replaced by SendGrid with the subscription management link

</td>
<td markdown="1">
[unsubscribe_tag]

</td>
</tr>
</table>

* * * * *


{% anchor h2 %} Twitter {% endanchor %}
 [API app name:"twitter"]

|Parameter|Description|Example|
|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
--|:---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---
layout: page
weight: 0
title: Filter Settings
navigation:
  show: true
---
---|
|username|Your Twitter username|username|
|password|Your Twitter password|password|


