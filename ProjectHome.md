**DropbProx**

Paulo Jerônimo (http://paulojeronimo.info)

# Summary #

**A GAE proxy to your Dropbox account.**

# Description #

The DropbProx aims to allow you to use your own domain to get files published in your [Dropbox](http://www.dropbox.com). So, after setting up your Dropbox account number at the application and publish it on Google App Engine (GAE), you will access your files in the Dropbox linking them to a more significant domain than that presented by URL `http://dl.dropbox.com/u/YOURDROPBOXNUMBER`.

This code is a very simple reduction/adaptation of [mirrorrr project](http://code.google.com/p/mirrorrr/) (by [Brett Slatkin](http://www.onebigfluke.com/)) held specifically to achieve the goals to build a proxy for public files from a user account in the Dropbox. If you want a full (and FREE) proxy to run on GAE, use the mirrorrr!

# Motivation #

I was looking for a FREE alternative to the problem described above. That's because I canceled my account on a virtual private server (VPS), which kept my domains. So, I could not use Apache 2 as [reverse proxy](http://clipmarks.com/clipmark/F469AE1E-29AB-44EF-8DBE-BF6C57CCDC26/) or his [mod\_rewrite](http://ubuntu-tutorials.com/2008/11/08/tinyurl-ify-dropbox-public-links-with-htaccess/) as a solution to this problem. With just a few searches on Google, I found a proxy written in Python (and able to run on GAE). Thus, I adapted his code to suit my needs.

# Installation #

  * Create a new project on GAE.
    * For example, I created a project named `pj74arqs`. A good tutorial about how to do this (for windows users) is the post "[Setup your own Proxy Server in 5 Minutes for Free](http://www.labnol.org/internet/setup-proxy-server/12890/)"
  * Change `application` variable at file `app.yaml` to the name of your created project on GAE;
  * Change `DROPBOX_NUMBER` variable at file `mirror.py` to your own Dropbox number;
  * Publish the application on GAE;
    * Windows users: see [this post](http://www.labnol.org/internet/setup-proxy-server/12890/);
  * _Optional_: Change the domain of the published application.
    * In my case, after publish the application, the domain was `pj74arqs.appspot.com`. But, this wasn't good for me yet. So, I changed the URL for that application to my subdomain: `a.paulojeronimo.com`. That was much better!

# Use #

  * Instead of access your files using the Dropbox URL (`http://dl.dropbox.com/u/YOURDROPBOXNUMBER`) you can now use the GAE application URL.
    * In my case, instead of access files at `http://dl.dropbox.com/u/345266`, I can now do that using `http://a.paulojeronimo.info`. For example, the files http://dl.dropbox.com/u/345266/curriculo/curriculo-pj.html and http://a.paulojeronimo.info/curriculo/curriculo-pj.html (my portuguese resume ;-) are the same, but the second is much more expressive, isn't it?
  * Update a file in your Dropbox account and refresh your URL. You will see that was updated in your proxy too!