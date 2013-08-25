---
layout: page
weight: 100
title: Marketing Email API Overview
navigation:
  show: true
---

SendGrid has a Marketing Email API that allows users to access data and interact with the Marketing Email functionality of SendGrid website. We also have a [Marketing Email web interface]({{root_url}}/Marketing_Emails/index.html).

The Marketing Email API provides developers with the ability to manage marketing emails, lists, identities, and schedule delivery events. This can be very useful in allowing development teams to propagate data in and out of the web based Marketing Email App that can be easily used by members of the company with little or no programming expertise.

The Marketing Email API is very similar to the Web API in that it follows the same convention and format, and utilizes the same technology; http requests. This is done with **http** requests to the SendGrid site with a variety of parameters to organize data. All query responses can be provided in either JSON or XML.  

* * * * *


{% anchor h2 %} URL Format {% endanchor %}


The following is the syntax for making Marketing Email API requests:

`     https://sendgrid.com/api/newsletter/[action].[format]`

-   **[action]** - Each module supports multiple actions such as add, get, and delete.
-   **[format]** - This determines the response format. It can be either json for a JSON response or xml for an XML response.

* * * * *


{% anchor h2 %} HTTP Return codes {% endanchor %}


-   **2XX** - The API call was successful.
-   **4XX** - The API call had an error in the parameters. The error will be encoded in the body of the response.
-   **5XX** - The API call was unsuccessful. You should retry later.


{% anchor h2 %} Responses {% endanchor %}


The formats supported are XML and JSON. Errors and success responses are described below while calls that provide information have their own return structure.


{% anchor h2 %} Errors {% endanchor %}


-   XML {% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result>
   <message>error</message>
   <errors>
      ...
      <error>... error messages ...</error>
      ...
   </errors>
</result>

{% endcodeblock %}
-   JSON {% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}

### Success

-   XML {% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result> success </result>

{% endcodeblock %}
-   JSON {% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}

* * * * *


{% anchor h2 %} Authentication {% endanchor %}


Each API call requires authentication. You must send the following HTTP parameters on your API calls. Your credentials are the same used for your SMTP authentication and/or website.

-   **api\_user** - This is the same credential used for your SMTP settings, and for logging into the website.
-   **api\_key** - This is the same password to authenticate over SMTP, and for logging into the website.

* * * * *

For detailed information on the available Marketing Email API methods, select one from the tree on the left.
