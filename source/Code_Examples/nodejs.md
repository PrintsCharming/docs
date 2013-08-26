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

<p>Once you have the module installed, it can be as simple as the following code snippet, modified to your specifics, of course:</p>


{% codeblock lang:javascript %}

var sendgrid  = require('sendgrid')(user, key);
sendgrid.send({
  to: 'example@example.com',
  from: 'other@example.com',
  subject: 'Hello World',
  text: 'My first email through SendGrid'
}, function(success, message) {
  if (!success) {
    console.log(message);
  }
});


{% endcodeblock %}


 
{% anchor h3 %} Digging In Deeper {% endanchor %}


Email is the object that will help you easily prepare your message to be sent.


{% info %} Anything that is available in the Email constructor is available for use in both the sendgrid.send and sendgrid.smtp functions. {% endinfo %}


To get started create an Email object:




{% codeblock lang:javascript %}

var Email = require('sendgrid').Email;
var email = new Email(optionalParams);


{% endcodeblock %}




You can pass in as many or as few optionalParams as you want, as the email object has methods for manipulating all of the data.

Here is how the parameters are structured:




{% codeblock lang:javascript %}

var optionalParams = {
  to: [],
  from: '',
  smtpapi: new SmtpapiHeaders(),
  subject: '',
  text: '',
  html: '',
  bcc: [],
  replyto: '',
  date: new Date(),
  files: [
    {
      filename: '',          // required only if file.content is used.
      contentType: '',       // optional
      path: '',              //
      url: '',               // == One of these three options is required
      content: ('' | Buffer) //
    }
  ],
  file_data: {},
  headers: {}
};


{% endcodeblock %}




And here is a sample for using it:




{% codeblock lang:javascript %}

var email = new Email({
  to: 'walks.it.in@sample.com',
  from: 'arsenal@sample.com',
  subject: 'What was Wenger thinking sending Walcott on that early?',
  text: 'Did you see that ludicrous display last night?'
});


{% endcodeblock %}


 
{% anchor h3 %} Setting data {% endanchor %}


Here is an example of all of the functions available on the email object. The comments to the right show the current state of the variables as the functions are called.




{% codeblock lang:javascript %}

var email = new Email({
  to: 'denim@sample.com',
  from: 'roy@sample.com',
  subject: 'Listen',
  text: 'Have you tried turning it off and on again'
});


{% endcodeblock %}




The following examples update the 'x-smtpapi' headers:




{% codeblock lang:javascript %}

/* To Addresses */
email.addTo('moo@cow.com');       // to = ['moo@cow.com']
email.addTo(['solid@snake.com',
            'liquid@snake.com']); // to = ['moo@cow.com', 'solid@snake.com', 'liquid@snake.com']

/* Custom Email Headers */
email.setHeaders({full: 'hearts'});   // headers = {full: 'hearts'}
email.addHeaders({spin: 'attack'});   // headers = {full: 'hearts', spin: 'attack'}
email.setHeaders({mask: 'salesman'}); // headers = {mask: 'salesman'}

/* Substitution */
email.addSubVal('keep', 'secret'); // sub = {keep: ['secret']}
email.addSubVal('keep', 'safe');   // sub = {keep: ['secret', 'safe']}

/* Section */
email.setSection({'-charge-': 'This ship is useless.'}); // section = {'-charge-': 'This ship is useless.'}
email.addSection({'-bomber-': 'Only for sad vikings.'}); // section = {'-charge-': 'This ship is useless.','-bomber-': 'Only for sad vikings.'}
email.setSection({'-beam-': 'The best is for first'});   // section = {'-beam-': 'The best is for first'}


{% endcodeblock %}




Setting unique arguments allows you to get more mojo out of your statistics:




{% codeblock lang:javascript %}

email.setUniqueArgs({cow: 'chicken'}); // unique_args = {cow: 'chicken'}
email.addUniqueArgs({cat: 'dog'});     // unique_args = {cow: 'chicken', cat: 'dog'}
email.setUniqueArgs({dad: 'proud'});   // unique_args = {dad: 'proud'}


{% endcodeblock %}




You can set categories with the following:




{% codeblock lang:javascript %}

email.setCategory('tactics');        // category = ['tactics']
email.addCategory('advanced');       // category = ['tactics', 'advanced']
email.setCategory('snowball-fight'); // category = ['snowball-fight']


{% endcodeblock %}




You can set a filter using an object literal:




{% codeblock lang:javascript %}

email.setFilterSetting({
  'footer': {
    'setting': {
      'enable': 1,
      'text/plain': 'You can haz footers!'
    }
  }
});


{% endcodeblock %}




Alternatively, you can add filter settings one at a time.




{% codeblock lang:javascript %}

email.addFilterSetting('footer', 'enable', 1);
email.addFilterSetting('footer', 'text/html', '<strong>boo</strong>');


{% endcodeblock %}




You can add files as attachments directly from content stored in memory, like so:




{% codeblock lang:javascript %}

email.addFile({
  filename: 'secret.txt',
  content:  new Buffer('You will never know....')
});


{% endcodeblock %}




Alternately, you can include files from a remote URL and will attempt to determine the file type based on the filename:




{% codeblock lang:javascript %}

email.addFile({
  filename: 'icon.jpg',
  url: 'http://i.imgur.com/2fDh8.jpg'
});


{% endcodeblock %}




Finally, you can add file from a path on the server's local filesystem, also attempting to determine the filetype via the filename:




{% codeblock lang:javascript %}

email.addFile({
  path: '../files/resume.txt'
});


{% endcodeblock %}


 
{% anchor h3 %} Testing Your Code {% endanchor %}


Tests located in the *test/lib* folder can be ran as-is and should all pass if your code is valid. Tests that are located in the *test/intergration* folder require valid SendGrid account credentials inserted into *test/test.setup* in order to run.


{% info %} Running tests requires a valid SendGrid account and will consume credits. {% endinfo %}


When you're ready, you can run your tests with this command:



{% codeblock %}
make test
{% endcodeblock %}

<p>You can run individual tests:</p>
{% codeblock %}
mocha /path/to/test.test.js
{% endcodeblock %}


