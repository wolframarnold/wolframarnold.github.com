---
title: "Selenium Installation & Setup"
layout: default
permalink: "/trainings/selenium/installation-setup"  	 
---


Selenium
========

The basic idea of Selenium is to script the interaction of human user with any website, or several websites.
Selenium test scripts can simulate input, clicks, move-overs and most things a human user can do with a web site.
Selenium then provides tools to verify that these user actions has the desired effect.  Selenium can check for page
loads, for text on the page to appear or disappear, for certain elements to be present or nor present, etc.

Selenium is also a fragmented playground of many different technologies.  In this training we focus on driving the browser through Ruby.

Editor/IDE
==========

Experience in teaching classes has shown that most students find it easiest to use an editor with project view
(i.e. a view of all the files in the directory in a side pane) or an IDE (Integrated Development Environment).

That way, there is less confusion about where to find the files, or what files to modify.  Some also offer syntax
highlighting.

Here are some useful free choices:

Free
----
* [Aptana Studio](http://www.brothersoft.com/aptana-studio-download-65879.html) (Max, Linux, Windows)
* [Komodo Edit](http://www.activestate.com/komodo-edit) (Max, Linux, Windows)
* [Notepad++](http://notepad-plus-plus.org/) (Windows only)
* [gedit](http://projects.gnome.org/gedit/) (Linux only, part of Gnome)

Commercial IDE's with free trial
---------------------------------
[Rubymine](http://www.jetbrains.com/ruby/download/) is my preferred editor and I'll use that for all the demos in class.

Operating System
================

Selenium and Ruby can be installed and run on any on the major operating systems (Max, Linux, Windows).  That said, things tend to be easier, faster and better supported on Mac and Linux.  If you have a laptop you want to bring, you may do so, and you can prepare by installing the software and tools on this page.  If you don't have an up-to-date
laptop, you can work off of our Ubuntu Linux machines which are well supported and very easy to use.  I run Ubuntu as primary operating system on my own laptop and will be using it throughout class.


Software Requirements
===================

Java
----

The Selenium Remote Control server runs on Java.  It thus runs on any operating system that supports a recent Java implementation.

We recommend the latest Java version from Sun/Oracle:

[http://java.com/en/download/](http://java.com/en/download/)

Ruby
----

Ruby is a powerful scripting language that also forms the basis for the popular Ruby-on-Rails web framework.  In this training,
we'll write Selenium test scripts in Ruby.

**Note: Use Ruby version 1.8.7, _not_ 1.9.x**

Follow these [Ruby Installation Instructions](http://www.ruby-lang.org/en/downloads/) according to your operating system (Windows, Mac, Linux)

Firefox
-------

We'll work with Firefox in this Training, although Selenium can also drive many other browsers.  Please be sure you have a recent version of Firefox installed.

[Firefox 3.6 download](http://www.mozilla.com/en-US/firefox/firefox.html)

RubyGems
--------

Gems are ruby packages, and RubyGems is Ruby's package management system. We'll be using several gems in the course of this training.
Please download the RubyGems package.

[RubyGems 1.3.7](http://rubyforge.org/frs/download.php/70697/rubygems-1.3.7.zip)

Once unzipped, open a command shell and run (via sudo or root on Mac & Linux):
{% highlight bash %}
  ruby setup.rb
{% endhighlight %}

For more information, see the [RubyGems Guide](http://docs.rubygems.org/read/chapter/3)

Gems
----

Now that the RubyGems package management system is installed, we can install gems from the Internet.
The RubyGems system already knows where to get them from, so all you need to do is this: (Use sudo or root on Mac & Linux)
{% highlight bash %}
  gem install rspec
  gem install rake
  gem install warnold-selenium-client
{% endhighlight %}

Almost Done
-----------

Now let's run a little smoke test to make sure everything is set up and ready to go.

Download:

[Selenium Tests Project](/downloads/selenium-course-tests.zip)

Unzip the archive, open a command shell and start the Selenium RC server

### on Windows

{% highlight ruby %}
java -jar vendor\selenium-remote-control\selenium-server.jar
{% endhighlight %}

### on Mac or Linux

{% highlight ruby %}
  rake selenium:rc:start  (This starts Selenium Remote Control in the background)
{% endhighlight %}

### Run the tests

Run the entire suite (all tests in the spec folder).  All test files must end in "_spec.rb" to be picked up by the suite.

{% highlight ruby %}
  rake spec               (This launches the test suite)
{% endhighlight %}

To run only one test, you can use _either one_ of the following:

{% highlight ruby %}
  rake spec SPEC=spec/my_test_spec.rb
  spec spec/my_test_spec.rb
{% endhighlight %}


If all goes well, you should see output like:
{% highlight bash %}
  1 example, 0 failures
{% endhighlight %}

And there is a report file in tmp, acceptance_tests_report.html
