---
layout: page
weight: 0
title: Subscription Tracking
navigation:
  show: true
---

Add automatic subscription management links to the bottom of emails. SendGrid will keep track of these unsubscribes and ensure these users don't get future emails from the sender.

![]({{root_url}}/images/subscription_tracking.png "docs_apps_subtrack_0212_tcr")

You can customize the text attached to emails and customize the landing page. The links will look something like the following, though can be configured in whatever fashion suits your needs:

{% codeblock %} sendgrid.net/submgmt/[encryptedString] {% endcodeblock %}

If you would like to customize your links, create a CNAME that points to sendgrid.net and fill out the Whitelabel setting (available for Silver accounts and higher) in your account.


{% anchor h2 %} API Settings {% endanchor %}


<table markdown="1" class="table table-bordered table-striped">
<tbody markdown="1">
<tr markdown="1">
<th markdown="1">
App Name

</th>
<th markdown="1">
Setting Field

</th>
<th markdown="1">
Required

</th>
<th markdown="1">
Description

</th>
</tr>
<tr markdown="1">
<td markdown="1">
subscriptiontrack

</td>
<td markdown="1">
enable

</td>
<td markdown="1">
YES

</td>
<td markdown="1">
0 to disable, 1 to enable

</td>
</tr>
<tr markdown="1">
<td markdown="1">
</td>
<td markdown="1">
text/html

</td>
<td markdown="1">
YES

</td>
<td markdown="1">
String for the HTML e-mail body

</td>
</tr>
<tr markdown="1">
<td markdown="1">
</td>
<td markdown="1">
text/plain

</td>
<td markdown="1">
YES

</td>
<td markdown="1">
String for the plain text e-mail body

</td>
</tr>
<tr markdown="1">
<td markdown="1">
</td>
<td markdown="1">
landing

</td>
<td markdown="1">
YES

</td>
<td markdown="1">
</td>
</tr>
<tr markdown="1">
<td markdown="1">
</td>
<td markdown="1">
replace

</td>
<td markdown="1">
No

</td>
<td markdown="1">
a tag that can be added to the content that will be replaced by SendGrid with the subscription management link, e.g. [unsubscribe\_tag]

</td>
</tr>
</tbody>
</table>

