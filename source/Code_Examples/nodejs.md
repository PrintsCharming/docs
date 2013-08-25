---
layout: page
weight: 0
title: Node.js
navigation:
  show: true
---

If you are using Node.js and would like to send email through SendGrid, use the SendGrid nodejs module. Full documentation for this module can be found on [github](http://github.com/sendgrid/sendgrid-nodejs).

{% codeblock %}
npm install sendgrid
{% endcodeblock %}

Once you have the module installed, it can be as simple as the following code snippet, modified to your specifics, of course:

 
{% anchor h3 %} Digging In Deeper {% endanchor %}


Email is the object that will help you easily prepare your message to be sent.


{% info %} Anything that is available in the Email constructor is available for use in both the sendgrid.send and sendgrid.smtp functions. {% endinfo %}


To get started create an Email object:



You can pass in as many or as few optionalParams as you want, as the email object has methods for manipulating all of the data.

Here is how the parameters are structured:



And here is a sample for using it:

 
{% anchor h3 %} Setting data {% endanchor %}


Here is an example of all of the functions available on the email object. The comments to the right show the current state of the variables as the functions are called.



The following examples update the 'x-smtpapi' headers:



Setting unique arguments allows you to get more mojo out of your statistics:



You can set categories with the following:



You can set a filter using an object literal:



Alternatively, you can add filter settings one at a time.



You can add files as attachments directly from content stored in memory, like so:



Alternately, you can include files from a remote URL and will attempt to determine the file type based on the filename:



Finally, you can add file from a path on the server's local filesystem, also attempting to determine the filetype via the filename:

 
{% anchor h3 %} Testing Your Code {% endanchor %}


Tests located in the *test/lib* folder can be ran as-is and should all pass if your code is valid. Tests that are located in the *test/intergration* folder require valid SendGrid account credentials inserted into *test/test.setup* in order to run.


{% info %} Running tests requires a valid SendGrid account and will consume credits. {% endinfo %}


When you're ready, you can run your tests with this command:

{% codeblock %}
make test
{% endcodeblock %}

You can run individual tests:

{% codeblock %}
mocha /path/to/test.test.js
{% endcodeblock %}
