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


<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">list</td>
<td align="left">A list of email addresses or domains.</td>
<td align="left">Ex: list[]=support@example.com&amp;list[]=sale@example.com}</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} BCC "Blind Carbon Copy" {% endanchor %}
 [API app name: "bcc"]

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">bcc</td>
<td align="left">An email address to be the BCC recipient.</td>
<td align="left">email@example.com</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} Click Tracking {% endanchor %}
 [API app name: "clicktrack"]

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">enable_text</td>
<td align="left">Enable click tracking in plain text emails.</td>
<td align="left">0|1</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} Domain Keys {% endanchor %}
 [API app name:"domainkeys"]

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">domain</td>
<td align="left">The domain to sign messages as</td>
<td align="left">example.com</td>
</tr>
<tr class="even">
<td align="left">sender</td>
<td align="left">1 to insert a sender header if the domain specified does not match the from address 0 to never insert a Sender header</td>
<td align="left">0|1</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} DKIM {% endanchor %}
 [API app name:"dkim"]

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Description</th>
      <th>Example</th>
   </tr>
   <td>domain</td>
   <td>The domain you would like your DKIM certification signed with</td>
   <td>example.com</td>
</table>


* * * * *


{% anchor h2 %} Email Templates {% endanchor %}
 [API app name:"template"]

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Description</th>
      <th>Example</th>
   </tr>
   <td>text\_html</td>
   <td>A string that holds the template html body</td>
   <td>Content</td>
</table>


* * * * *


{% anchor h2 %} Event Notification {% endanchor %}
 [API app name:"eventnotify"] 
{% info %} All fields are required for each call. {% endinfo %}


<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">processed</td>
<td align="left">Notify when email is processed</td>
<td align="left">0|1</td>
</tr>
<tr class="even">
<td align="left">dropped</td>
<td align="left">Notify when email is dropped</td>
<td align="left">0|1</td>
</tr>
<tr class="odd">
<td align="left">deferred</td>
<td align="left">Notify when email is deferred</td>
<td align="left">0|1</td>
</tr>
<tr class="even">
<td align="left">delivered</td>
<td align="left">Notify when email is delivered</td>
<td align="left">0|1</td>
</tr>
<tr class="odd">
<td align="left">bounce</td>
<td align="left">Notify when email is bounced</td>
<td align="left">0|1</td>
</tr>
<tr class="even">
<td align="left">click</td>
<td align="left">Notify when email is clicked</td>
<td align="left">0|1</td>
</tr>
<tr class="odd">
<td align="left">open</td>
<td align="left">Notify when email is opened</td>
<td align="left">0|1</td>
</tr>
<tr class="even">
<td align="left">unsubscribe</td>
<td align="left">Notify when email is unsubscribed</td>
<td align="left">0|1</td>
</tr>
<tr class="odd">
<td align="left">spamreport</td>
<td align="left">Notify when email is marked as spam</td>
<td align="left">0|1</td>
</tr>
<tr class="even">
<td align="left">url</td>
<td align="left">The post notification url to post these event messages to</td>
<td align="left">url=http://yourPostNotificationUrl.example.com</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} Footer {% endanchor %}
 [API app name:"footer"]

<table class="table table-bordered table-striped">
   <tr>
      <th>Parameter</th>
      <th>Description</th>
      <th>Example</th>
   </tr>
   <tr>
      <td>text/html</td>
      <td>String that holds the html body</td>
      <td>Content</td>
   </tr>
   <tr>
      <td>text/plain</td>
      <td>String that holds the text body</td>
      <td>Content</td>
   </tr>
</table>


* * * * *


{% anchor h2 %} Google Analytics {% endanchor %}
 [API app name:"ganalytics"]

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">utm_source</td>
<td align="left">Name of the referrer source</td>
<td align="left">Google, SomeDomain.com, or Marketing EmailA</td>
</tr>
<tr class="even">
<td align="left">utm_medium</td>
<td align="left">Name of the marketing medium</td>
<td align="left">Email, Affiliate, or MobileApp</td>
</tr>
<tr class="odd">
<td align="left">utm_campaign</td>
<td align="left">Name of the campaign</td>
<td align="left">Quarter1, FallShoeSale</td>
</tr>
<tr class="even">
<td align="left">utm_term</td>
<td align="left">Identify paid keywords</td>
<td align="left">Poultry, Health</td>
</tr>
<tr class="odd">
<td align="left">utm_content</td>
<td align="left">Use to differentiate ads</td>
<td align="left">PageA, PageB</td>
</tr>
</tbody>
</table>

* * * * *


{% anchor h2 %} Gravatar {% endanchor %}
 [API app name:"gravatar"]

<table class="table table-bordered table-striped">
   <th>Parameter</th>
   <th>Description</th>
   <th>Example</th>
</table>


* * * * *


{% anchor h2 %} Open Tracking {% endanchor %}
 [API app name:"opentrack"]

<table class="table table-bordered table-striped">
   <th>Parameter</th>
   <th>Description</th>
   <th>Example</th>
</table>


* * * * *


{% anchor h2 %} Return Path Seedlist {% endanchor %}
 [API app name:"seedlist"]

<table class="table table-bordered table-striped">
   <th>Parameter</th>
   <th>Description</th>
   <th>Example</th>
</table>


* * * * *


{% anchor h2 %} SPAM Filter Checker {% endanchor %}
 [API app name:"spamcheck"]

<table class="table table-bordered table-striped">
   <th>Parameter</th>
   <th>Description</th>
   <th>Example</th>
</table>


* * * * *


{% anchor h2 %} Subscription Tracking {% endanchor %}
 [API app name:"subscriptiontrack"]

<table class="table table-bordered table-striped">
   <th>Parameter</th>
   <th>Description</th>
   <th>Example</th>
</table>


* * * * *


{% anchor h2 %} Twitter {% endanchor %}
 [API app name:"twitter"]

<table>
<thead>
<tr class="header">
<th align="left">Parameter</th>
<th align="left">Description</th>
<th align="left">Example</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">username</td>
<td align="left">Your Twitter username</td>
<td align="left">username</td>
</tr>
<tr class="even">
<td align="left">password</td>
<td align="left">Your Twitter password</td>
<td align="left">password</td>
</tr>
</tbody>
</table>


