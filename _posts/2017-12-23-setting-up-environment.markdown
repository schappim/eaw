---
layout: post
title:  "Setting up our Environment"
date:   2017-12-23 08:07:43 +1100
categories: jekyll update
---

For hacking around I like to use [Digital Ocean](https://www.digitalocean.com) (based out of the) and [Binary Lane](https://www.binarylane.com.au) (if my project is sensitive to latency). 

I like to use [Ubuntu](https://www.ubuntu.com) Servers as they're well supported. 

## SSH-ing to our Server

We connect to our server using SSH (Secure Shell).

The `ssh` command takes the format: 

```
ssh username@server.com
```

When we use this command we'll be prompted to enter a password each time. 

We can get around this by creating using *SSH Keys*.

#### Creating an SSH Key


```
ssh-keygen -t rsa
```

Your private key is saved to the `id_rsa` file in the `.ssh` directory and is used to verify the public key you use belongs to the same account.


#### Installing your SSH Key


Your public key is saved to the `id_rsa.pub`; file and is the key. You can save this key to the clipboard by running this:

```
pbcopy < ~/.ssh/id_rsa.pub
```

Note: `pbcopy` is a mac command that takes content from the command line and puts it on your clipboard. 

You could also do this command: 

```
cat ~/.ssh/id_rsa.pub | pbcopy
```

to achieve the same result. 

<script src="https://asciinema.org/a/sRUGCGwXxLazcEIhw9RQhbbVa.js" id="asciicast-sRUGCGwXxLazcEIhw9RQhbbVa"   data-rows="25"  async></script>


#### Actually SSHing into your Box

<script src="https://asciinema.org/a/JUmgYZXUPOwu2U1GwBZpA6x20.js" id="asciicast-JUmgYZXUPOwu2U1GwBZpA6x20"  data-rows="25"  async></script> 

#### Further Reading

Here are some links on creating an SSH Key for your OS of choice: 

* [Creating a SSH Key on Windows](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-windows)
* [Creating a SSH Key on MacOS](https://docs.joyent.com/public-cloud/getting-started/ssh-keys/generating-an-ssh-key-manually/manually-generating-your-ssh-key-in-mac-os-x)

## Installing Software

To install software on Ubuntu we use the `apt` command.

APT stands for *Advanced Package Tool*, and it handles the installation and removal of software on Debian and other Linux distributions (hear [Ubuntu](https://www.ubuntu.com), [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) for Raspberry Pi etc). We are using Ubuntu.

We need to run `apt` as `root`. If we're logging in as `root` we can just use the program, but if we're a normal user we need to use `sudo`. 

The program `sudo` stands for *super user do*, and it elevates the privledges of a standard user to that of a super user. Use `sudo` before a command to do this. 

On your Mac or PC try this: 

```
whoami
```

Then try
```
sudo whoami
```

notice a difference?

<script src="https://asciinema.org/a/OLOqEZNLyJXOexNTukrj6yEQS.js" id="asciicast-OLOqEZNLyJXOexNTukrj6yEQS"  data-rows="25"  async></script> 

#### apt-get update and apt-get upgrade

`apt-get update` doesn't actually install new versions of software. Instead, it updates the package lists for upgrades for packages that need upgrading, as well as new packages that have just come to the repositories.

`apt-get upgrade` upgrades packages that need upgrading.
<script src="https://asciinema.org/a/bKsQzccIAJmBzjNHI6cOpBO3t.js" id="asciicast-bKsQzccIAJmBzjNHI6cOpBO3t"   data-rows='25' async></script> 


#### Installing Packages

`sudo apt-get install cmatrix`

<script src="https://asciinema.org/a/UDFnamQl20QYq42UuuAq1XOEo.js" id="asciicast-UDFnamQl20QYq42UuuAq1XOEo"  data-rows="25"  async></script> 

#### Removing Packages

`sudo apt remove cmatrix`

<script src="https://asciinema.org/a/7tmiyLg1ppVwNtOw4E4rvOzRE.js" id="asciicast-7tmiyLg1ppVwNtOw4E4rvOzRE"  data-rows="25"  async></script> 


#### Installing Packages

We need to install `ruby2.3-dev` and `build-essential`. 

Ruby is a programming language (god's gift to programmers) and the `build-essential` package has a series of compiler and tools required for building compiled software.

<script src="https://asciinema.org/a/Bcxv4gpI9E4AD7TfpQhcoRCQ1.js" id="asciicast-Bcxv4gpI9E4AD7TfpQhcoRCQ1"   data-rows='25' async></script> 


