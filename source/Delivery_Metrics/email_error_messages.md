--- layout: page weight: 0 title: Email Error Messages navigation: show:
true ---

When you send an email, it must be accepted by the recipients mail
server before anything else happens. These mail servers will always
respond with numerical error messages to tell you the reason a
particular mail server handled the message the way it did. Different
mail servers use different phrasing for error messages, but the numeric
codes are always the same.

On the [Email Activity](http://sendgrid.com/logs/index) page, you can
expand specific events to see the messages returned by the receiving
mail server. Remember you can filter by specific email addresses by
using the search field provided. You may also filter your search to only
populate specific event types such as Requests, Bounces, Deferrals and
Drops.

![]({{root_url}}/images/email_error_messages.png)

You can also use the [Email Lists](http://sendgrid.com/bounces/) to view
the messages returned for the specific event categories listed there.

Listed below are some examples of messages you are likely to see, along
with a brief description of what caused the error to be returned.

{% anchor h2 %} 200's {% endanchor %}

-   250 – Requested action taken and completed. This message is your
    friend.
-   251 – The recipient is not local to the server, but the server will
    accept and forward the message.
-   252 – The recipient cannot be VRFYed, but the server accepts the
    message and attempts delivery.

{% anchor h2 %} 400's {% endanchor %}

-   421 – The service is not available and the connection will be
    closed.
-   450 – The requested command failed because the user's mailbox was
    unavailable.
-   451 – The command has been aborted due to a server error on the
    recipient side.
-   452 – The command has been aborted because the server has
    insufficient system storage.

{% anchor h2 %} 500's {% endanchor %}

-   500 – The server could not recognize the command due to a syntax
    error.
-   501 – A syntax error was encountered in command arguments.
-   502 – This command is not implemented.
-   503 – The server has encountered a bad sequence of commands.
-   504 – A command parameter is not implemented.
-   550 – The requested command failed because the user's mailbox was
    unavailable
-   551 – The recipient is not local to the mail server.
-   552 – The action was aborted due to storage capacity allowances.
-   553 – The command was aborted because the mailbox name is invalid.
-   554 – The transaction failed, often for reasons unknown.

The messages you see may vary from domain to domain, so be sure to read
the error reasons in addition to referencing this list.
