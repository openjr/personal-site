---
title: "Storing Git Credentials on Ubuntu"
date: 2019-06-04T20:49:26-04:00
draft: false
---


Recently I stop using my Hackintosh and replaced it with Ubuntu 18, however
the first thing that I noticed is that it would prompt me for my GitHub credentials
every time I do a pull/push using the CLI which is annoying.

The way I found to solve this is based in this [Stack Overflow Question](https://askubuntu.com/questions/773455/what-is-the-correct-way-to-use-git-with-gnome-keyring-and-https-repos) (paint me surprised) 
which in short becomes 

```bash
sudo apt-get install libsecret-1-0 libsecret-1-dev
cd /usr/share/doc/git/contrib/credential/libsecret
sudo make
git config --global credential.helper /usr/share/doc/git/contrib/credential/libsecret/git-credential-libsecret
```


After doing so, I just had to put my username and password once more and the problem
got solved, yay!

