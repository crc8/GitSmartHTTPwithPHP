Git Smart HTTP with PHP
=======================

Introduction
------------

(Sorry for my english)

After evaluated several possible cloud storage based solutions like Amazon S3, Google Drive & Dropbox as my private git repo. I find these solutions don`t really suit my needs. As each of them requires you to either install a client, mount the storage, manual/auto sync the contents etc.

Then I explored Git smart http as potential candidate as it provides much simplier solution to my need. All I have to do is to install a Git client then I`m set to push my repo into my centralized Git (with smart http) repository on my own hosting server. However, setting it up was a bit cumbersome (httpd.conf etc) and can be improved better.

Therefore I come out this single PHP file that act as middle man to handle request between your git client and git smart http backend.

Now with only Git installed on the computer, you are ready to work with your project. :)

Requirement
-----------

- Web server with Git (> v1.6.6) and PHP (> v5) installed

Setup
-----

1. Make sure your web server has Git installed and your web server supports PHP

2. Upload `git.php` onto your hosting directory (Eg. /home/my/public_html/git.php)

3. Create a folder (Eg. /home/my/public_html/repo) for all your git repositories storage.

4. `chown apache:apache git.php` and `chown apache:apache repo`

5. Proceed to `http://<yoursite>/git.php?admin` to init a repo and to manage them

6. With `git remote add origin http://<yoursite>/git.php/<reponame>`, you can push your local git repo to your private repo online.

Todo
----

- Explain debug log feature

- Explain http auth feature

- Explain gzip support feature