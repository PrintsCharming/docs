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


<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>list</td>
         <td>A list of email addresses or domains.</td>
         <td>Ex: list[]=support@example.com&amp;list[]=sale@example.com}</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} BCC "Blind Carbon Copy" {% endanchor %}
 [API app name: "bcc"]

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>bcc</td>
         <td>An email address to be the BCC recipient.</td>
         <td>email@example.com</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} Click Tracking {% endanchor %}
 [API app name: "clicktrack"]

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>enable_text</td>
         <td>Enable click tracking in plain text emails.</td>
         <td>0|1</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} Domain Keys {% endanchor %}
 [API app name:"domainkeys"]

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>domain</td>
         <td>The domain to sign messages as</td>
         <td>example.com</td>
      </tr>
      <tr>
         <td>sender</td>
         <td>1 to insert a sender header if the domain specified does not match the from address 0 to never insert a Sender header</td>
         <td>0|1</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} DKIM {% endanchor %}
 [API app name:"dkim"]



* * * * *


{% anchor h2 %} Email Templates {% endanchor %}
 [API app name:"template"]



* * * * *


{% anchor h2 %} Event Notification {% endanchor %}
 [API app name:"eventnotify"] 
{% info %} All fields are required for each call. {% endinfo %}


<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>processed</td>
         <td>Notify when email is processed</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>dropped</td>
         <td>Notify when email is dropped</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>deferred</td>
         <td>Notify when email is deferred</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>delivered</td>
         <td>Notify when email is delivered</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>bounce</td>
         <td>Notify when email is bounced</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>click</td>
         <td>Notify when email is clicked</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>open</td>
         <td>Notify when email is opened</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>unsubscribe</td>
         <td>Notify when email is unsubscribed</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>spamreport</td>
         <td>Notify when email is marked as spam</td>
         <td>0|1</td>
      </tr>
      <tr>
         <td>url</td>
         <td>The post notification url to post these event messages to</td>
         <td>url=http://yourPostNotificationUrl.example.com</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} Footer {% endanchor %}
 [API app name:"footer"]



* * * * *


{% anchor h2 %} Google Analytics {% endanchor %}
 [API app name:"ganalytics"]

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>utm_source</td>
         <td>Name of the referrer source</td>
         <td>Google, SomeDomain.com, or Marketing EmailA</td>
      </tr>
      <tr>
         <td>utm_medium</td>
         <td>Name of the marketing medium</td>
         <td>Email, Affiliate, or MobileApp</td>
      </tr>
      <tr>
         <td>utm_campaign</td>
         <td>Name of the campaign</td>
         <td>Quarter1, FallShoeSale</td>
      </tr>
      <tr>
         <td>utm_term</td>
         <td>Identify paid keywords</td>
         <td>Poultry, Health</td>
      </tr>
      <tr>
         <td>utm_content</td>
         <td>Use to differentiate ads</td>
         <td>PageA, PageB</td>
      </tr>
   </tbody>
</table>


* * * * *


{% anchor h2 %} Gravatar {% endanchor %}
 [API app name:"gravatar"]



* * * * *


{% anchor h2 %} Open Tracking {% endanchor %}
 [API app name:"opentrack"]



* * * * *


{% anchor h2 %} Return Path Seedlist {% endanchor %}
 [API app name:"seedlist"]



* * * * *


{% anchor h2 %} SPAM Filter Checker {% endanchor %}
 [API app name:"spamcheck"]



* * * * *


{% anchor h2 %} Subscription Tracking {% endanchor %}
 [API app name:"subscriptiontrack"]



* * * * *


{% anchor h2 %} Twitter {% endanchor %}
 [API app name:"twitter"]

<table class="table table-bordered table-striped">
   <thead>
      <tr>
         <th>Parameter</th>
         <th>Description</th>
         <th>Example</th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td>username</td>
         <td>Your Twitter username</td>
         <td>username</td>
      </tr>
      <tr>
         <td>password</td>
         <td>Your Twitter password</td>
         <td>password</td>
      </tr>
   </tbody>
</table>



