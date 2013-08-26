---
layout: page
weight: 0
title: Ruby on Rails
navigation:
  show: true
---

This Rails example shows how to send an email for user signups. You can also checkout [this Ruby gem](https://github.com/stephenb/sendgrid) for more advanced features.


{% info %} This example is specific to ActionMailer. You can use any SMTP library that is compatible with Rails, but the configuration may be slightly different. {% endinfo %}
 In **config/environment.rb** specify ActionMailer defaults {% codeblock lang:ruby %} ActionMailer::Base.smtp_settings = { :user_name =\> 'sendgridusername', :password =\> 'sendgridpassword', :domain =\> 'yourdomain.com', :address =\> 'smtp.sendgrid.net', :port =\> 587, :authentication =\> :plain, :enable_starttls_auto =\> true } {% endcodeblock %} 
{% warning %} As a best practice, you should not store your credentials directly in the source but should instead store them in configuration files or environment variables. See this tutorial on [environment variables in rails](http://railsapps.github.io/rails-environment-variables.html). {% endwarning %}
 Create your notification model in **app/models/notifier.rb** {% codeblock lang:ruby %} class Notifier \< ActionMailer::Base default :from =\> 'any_from_address@example.com' \# send a signup email to the user, pass in the user object that contains the user's email address def signup_email(user) mail( :to =\> user.email, :subject =\> 'Thanks for signing up' ) end end {% endcodeblock %} In the controller in **app/controllers/users_controller.rb** add {% codeblock lang:ruby %} class UsersController \< ApplicationController def create \# Create the user from params @user = User.new(params[:user]) if @user.save \# Deliver the signup_email Notifier.signup_email(@user).deliver redirect_to(@user, :notice =\> 'User created') else render :action =\> 'new' end end end {% endcodeblock %}
