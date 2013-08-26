---
layout: page
weight: 100
title: Web API Overview
navigation:
  show: true
---

SendGrid offers a Web API that allows customers to retrieve information about their account such as statistics, bounces, spam reports, unsubscribes, and other information. This API is not RESTful since for most calls both GET and POST HTTP verbs can be used interchangeably, and other verbs are not supported.

* * * * *


{% anchor h2 %} URL Format {% endanchor %}


The following is the syntax for making Web API requests:

` 	https://sendgrid.com/api/[module].[action].[format]`

-   **[module]** - The API endpoint to call, e.g. blocks.
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


-   XML 
{% codeblock lang:xml %}
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

-   JSON 
{% codeblock lang:javascript %}
{
  "message": "error",
  "errors": [
    "...error messages..."
  ]
}
{% endcodeblock %}


### Success

-   XML 
{% codeblock lang:xml %}
<?xml version="1.0" encoding="ISO-8859-1"?>

<result> success </result>

{% endcodeblock %}

-   JSON 
{% codeblock lang:javascript %}
{
  "message": "success"
}
{% endcodeblock %}


* * * * *


{% anchor h2 %} Authentication {% endanchor %}


Each API call requires authentication. You must send the following HTTP parameters on your API calls. Your credentials are the same used for your SMTP authentication and/or website.

-   **api_user** - This is the same credential used for your SMTP settings, and for logging into the website.
-   **api_key** - This is the same password to authenticate over SMTP, and for logging into the website.

* * * * *

For detailed information on the available Web API methods, select one from the tree on the left.
