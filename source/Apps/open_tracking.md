--- layout: page weight: 0 title: Open Tracking navigation: show: true
---

The Open Tracking app adds an invisible image at the end of the email
which can track e-mail opens. If the email recipient has images enabled
on the email client, a request to server for the invisible image is
executed and an open event is logged. These Events are logged in your
[Statistics]({{root_url}}/Delivery_Metrics/) portal, the [Email
Activity]({{root_url}}/Delivery_Metrics/email_activity.html) interface,
and are reported by the [Event
Webhook]({{root_url}}/API_Reference/Webhooks/event.html).

![]({{root_url}}/images/open_tracking.png "open-fixed")

When using this service customers often ask the difference between a
unique open versus an open. A unique open is logged only the first time
a given recipient opens the email whereas normal opens are logged for
all opens of the email in question.

{% anchor h2 %} Settings {% endanchor %} There are no settings for this
App.
