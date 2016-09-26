---
layout: post
title:  "Why do I use Fish Shell 99% of the time!"
date:   2016-09-25 17:07:15
categories: development
author: hsyn
image: img/fish-shell.png
---

I am using Fish Shell as my main shell and I started doing it after a year of working with Bash as a developer. Don't get me wrong, Bash is still my second choice and I really need it sometimes.

But let me explain what kind of advantages FIsh Shell gives me over other alternatives, and I will let you decide if it is worth switching.

First and foremost, Fish Shell has sane defaults. You can almost call it an opinionated software in a good way. I personally find it similar to Apple products. It has its own way of dealing with everyday things, and boy they are so good!

Let's start with basics.

- #### Built-in git support

  ![Fish-shell-git-support](/img/fish-shell-git-support.png)

  It will automatically detect when you are in a git tracked folder and you can customize your promt to tell you what you want to see. Which will also take you the second point.

- #### Web based configuration interface

  Fish will let you customize your color scheme, prompt, and history via web based interface. All you have to do is type `fish_config` on your command line and it will start a local web server and open the GUI with your default editor.

  ![Fish-shell-web-gui](/img/fish-shell-web-gui.png)

- #### Wonderful history search

  This is one of my favorite features of Fish Shell. You type some part of the command, and then press the ↑ (up) or ↓(down) arrow keys to navigate history matches. For example, starting postgres server, just type `pos` and ↑ will take you to where you want. Type `server10` and ↑ will take you to latest interaction to that server. Continue pressing to go deeper into history.

  ![Fish-shell-search-gif](/img/fish-shell-search.gif)

- #### Auto suggestions

  Fish Shell will give you suggestions as you type your commands, and even will highlight what you might want to type.

  ![Fish-shell-auto-suggestions-gif](/img/fish-shell-auto-suggestions.gif)

  It will even parse the man pages of the installed command line programs for you and will let list you those commands when you use TAB completion. The more you use it the more it will know about you and wil be more efficent. It will also let you know if the command or the path exists while you typing by changing the color of the command.


  ![Fish-shell-man-page](/img/fish-shell-man-page.png)

- #### Conclusion

  As I mentioned at the begining of the article, sometimes I just get lazy and use bash shell when i don't want to convert bash syntax to fish compatible version. I do it by just typing `bash` in the current session and it drops me in the same directory as I was in the fish session. And type `exit` when you wanna go back to fish shell again. There are lots of other features that i did not mention in this post but you can go to [their page and read more about it.](http://fishshell.com/){:target="_blank"}

  I also tried Zsh and some other shells but they all required too much configuration to work as expected and I prefer spending my time on focusing other things instead of keeping my shell up to date.

  I really recommend you to take a look at [Fish Shell Desing Principles](http://fishshell.com/docs/current/design.html){:target="_blank"} documentation where they explained their philosophy in an excellent way. And there is also an [excellent discussion](https://news.ycombinator.com/item?id=11102941){:target="_blank"} on Hackernews if you want to read it. This reply from `xiaq` puts it better than I would about why I chose fish over zsh shell.

  ![Fish-shell-configurability](/img/fish-configurability.png)

  Cheers!
