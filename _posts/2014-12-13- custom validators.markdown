---
layout: post
title: "Custom Validators"
date:   2014-12-13 12:00:00
categories: Rails
tags: featured
image:
---

* topics :rails, :validators, :AARP

Validators are really powerful, they allow us to do some really cool things and help prevent users or Mallory from editing content that they should not be allowed to. Rails provides us will all kinds of validations with the validates method, however sometimes we need our own custom validation method. One of the ways we can do this is with, the validates_with method. 

Below is an example from my ScheduleME passion project for Metis.

In my code I have the ability for a manager user to change another user’s role. However if that user is a owner, then their role can not be changed, they are always a manager. 

So with that logic lets get started. 

In your class you want declare it along with the other validations of the class. 

{% highlight ruby %}
class User "<" ActiveRecord::Base
  validates :email, presence: true, uniqueness: true
  validates :username, presence: true, uniqueness: true
  validates :password_digest, presence: true
  validates :role, presence: true
  validates_with OwnerValidator
{% endhighlight %}

The validates with method takes a class as its parameter. So we have to create a class called OwnerValidator. However we have a problem, where do we create that class at? Its not a view or a model and its definitely not a controller. The most logical place to put it would be in app/validators so lets create that directory and then create our file owner&#95;validator.rb. We should now have app/validators/owner&#95;validator.rb

ok lets add the content of the class. 

{% highlight ruby %}
class OwnerValidator '<' ActiveModel::Validator
  def validate(record)
    if record.owner?
      record.errors[:owner] << "role can not be changed"
    end
  end
end
{% endhighlight %}

I extended ActiveModel::Validator. Our validator comes with a validate method which has a parameter called record. From there I simply asked if the user is a owner?, this predicate method comes with user because owner is a boolean column on user. So if the user being edited is a owner then it will shovel my error message in to the owner attribute of the error hash.

Ok were done...wait its not working, this is because rails does not see our app/validator directory. We have to fix this in config/application.rb

add
{% highlight ruby %}
config.autoload_paths += %w[#{config.root}/app/validators] 
{% endhighlight %}
bellow
{% highlight ruby %}
module ScheduleME
  class Application '<' Rails::Application
{% endhighlight %} 

Restart your server and now rails will be able to find your custom validators.
