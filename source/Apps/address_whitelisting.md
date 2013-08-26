---
layout: page
weight: 0
title: Address Whitelisting
navigation:
  show: true
---

The Address Whitelist App whitelists a specified e-mail address or domain for which mail should never be suppressed. For example, you own the domain example.com, and one or more of your recipients use email@example.com addresses, by placing example.com in the Address Whitelist App, all bounces, blocks and unsubscribes logged for that domain will be ignored and sent to as if under normal sending conditions.

![Address Whitelist App Image]({{root_url}}/images/address_whitelist.png "Address Whitelist")


{% anchor h2 %} Settings {% endanchor %}


|Name|Required|Description|
|:---|:-------|:----------|
|Email|Yes|Adds the entered domain or address to the list of those that should never be suppressed.|

There is no practical limit to the number of domains you add in this way.
