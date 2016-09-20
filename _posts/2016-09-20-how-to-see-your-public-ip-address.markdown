---
layout: post
title:  "How to see your public IP address"
date:   2016-09-19 19:38:10
categories: internet
author: hsyn
image: img/no-place-like-home.jpg
---

Here are some easy ways for you to see your public IP address.


##### Command-line
{% highlight console %}
  dig +short myip.opendns.com @resolver1.opendns.com
{% endhighlight %}

You can use some other services like [icanhazip.com](http://icanhazip.com){:target="_blank"} to write something like `curl icanhazip.com` but DNS servers historically more reliable and will not let you down 99% of the time :ok_hand:!

PS: DNS response will be 10x times faster than http responses so you save some precious miliseconds :trollface:

For those who are not using [Fish Shell](http://fishshell.com/docs/current/tutorial.html){:target="_blank"} or will not remember the code block above all the time, here is a solution for that.

Bind an alias string to something like "myip" so next time you only type your alias instead of the whole block.

{% highlight console %}
  alias myip "dig +short myip.opendns.com @resolver1.opendns.com"
{% endhighlight %}

----

##### Browser
Alrite project managers, command line is really your sharpest tool, I get it. Here are some easy ways for you to determine what your IP address is.

If you are using Google Chrome as your browser, [googling "my ip"](https://www.google.com/search?q=my+ip){:target="_blank"} will directly show your IP address.

![google result](/img/ip_adress_google.png)

For Safari, Firefox, Internet Explorer users, there are lots of sites to reveal this information. Google's support page suggests these 2:

- [whatsmyip.org](http://whatsmyip.org){:target="_blank"}

- [whatsmyip.com](http://whatismyip.com){:target="_blank"}


----


Cheers!
