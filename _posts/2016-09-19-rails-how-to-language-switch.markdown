---
layout: post
title:  "How to implement locale switch on your app"
date:   2016-09-19 19:38:10
categories: rails
author: hsyn
image: img/multilingual-rails.png
---

I recently worked on a project and one of the requirements in to-do list was application's being multilingual.

I came up with a fairly easy solution on how to implement it. Here it comes;


First define your locale values.


###### `config/application.rb`
{% highlight ruby%}
  # set default locale
  config.i18n.default_locale = :sv
  # set available locales
  config.i18n.available_locales = [:sv, :en]

{% endhighlight %}
----

Now lets implement reques/response part.


###### `app/controllers/application_controller.rb`
{% highlight ruby%}

  before_action :set_locale

  private

  def set_locale
    # specify the order of where to fetch locale value.
    # first check params, if not then check session, otherwise fallback to default locale.
    locale = params[:locale] || session[:locale] || I18n.default_locale
    # set locale if it exists in available locales list
    I18n.locale = I18n.locale_available?(locale) ? locale : I18n.default_locale
    # update session value so we don't need to carry locale all the time in the url
    session[:locale] = I18n.locale
  end

  def default_url_options(options={})
    # update default url if it default locale is not in use currently.
    locale = I18n.default_locale == I18n.locale ? nil : I18n.locale
    { locale: locale }.merge options
  end

{% endhighlight %}
----

Jump into your routes file and scope all your route definitions into a scope

###### `config/routes.rb`
{% highlight ruby%}

  scope "(:locale)", locale: /#{I18n.available_locales.join("|")}/ do
    root 'home#index'
    ...
  end

{% endhighlight %}
----

And in your `layout` file, you can just add those locales as a query parameter to list of links

###### `app/views/layouts/application.html.slim`
{% highlight slim%}

  ul.menu
    li
      = link_to "English", locale: "en"
    li
      = link_to "Svenska", locale: "sv"


{% endhighlight %}
---

Thats it! Now, go get some coffee :)
