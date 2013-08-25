--- layout: page weight: 0 title: Domain Keys navigation: show: true ---

Some ISPs (most notably Yahoo!) authenticate e-mail using Domain Keys.
Domain Keys work by having a company sign an e-mail with their private
key, and then publish a public key in their DNS, which is then used to
verify the e-mail signature.

The domain that is checked for the public key is based on one of two
e-mail headers; Sender and From. If a Sender header is specified, its
domain will be the first one checked, otherwise the domain of the From
header will be used. Most e-mail clients do not insert a Sender header,
so typically the From address would be used.

![Domain Keys App
Image]({{root_url}}/images/domain_keys.png "Domain Keys")

By default, SendGrid signs all e-mail with Domain Keys to improve its
deliverability, however for accounts that do not have Whitelabeling
enabled the domain in the From field will not have the proper DNS record
to authenticate the e-mail. Because of this SendGrid inserts a Sender
header and the e-mail can then be properly authenticated.

{% anchor h2 %} Settings {% endanchor %}

<table>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Required</th>
<th align="left">Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Domain</td>
<td align="left">Yes</td>
<td align="left">Sets the sender domain.</td>
</tr>
<tr class="even">
<td align="left">Enable sender header</td>
<td align="left">Yes</td>
<td align="left">Enables the Domain Keys sender header.</td>
</tr>
</tbody>
</table>

Some ISPs or e-mail clients (such as Hotmail or Outlook) will display a
message with the Sender header reading "on behalf of" followed by the
address that is in the Sender header. To remove this, do one of the
following:

1.Disable the Domain Keys filter in the filters section of your account

2.Upgrade to a package (Silver or higher) that provides
[Whitelabel](http://sendgrid.com/whitelabel/) support and set up the
Domain Keys record in your DNS
