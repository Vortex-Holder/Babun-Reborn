# Babun - The Reborn of a Good Terminal [PROJECT REBORN]
Want to use a Linux-like console on your Windows computer? Try Babun Reborn!
By [Alts Studio](https://gamejolt.com/@AltsStudio)
## Installation
Visit this site to download https://altsstudio.itch.io/babun-reborn
The application will be installed to the ```%USER_HOME%\.babun``` directory.
| Note | Installation instructions are available on the download site. |
| :--- | :--- |

| Note | Babun Reborn was produced by Alts Studio. |
| :--- | :--- |
## Features
Babun features the following:

* Pre-configured Cygwin with a lot of addons

* Silent command-line installer, no admin rights required

* pact - advanced package manager (like apt-get or yum)

* xTerm-256 compatible console

* HTTP(s) proxying support

* Plugin-oriented architecture

* Pre-configured git and shell

* Integrated oh-my-zsh

* Auto update feature

* "Open Babun Here" context menu entry

  Have a look at a sample screenshot!

<img width="1365" height="729" alt="image" src="https://github.com/user-attachments/assets/9a00c3f1-d921-48ad-ba07-d4b497b17010" />

Do you like it? Follow Alts Studio on Gamejolt [Alts Studio](https://gamejolt.com/@AltsStudio)

## Features in 5 minutes
### Cygwin
The core of Babun consists of a pre-configured Cygwin. Cygwin is a great tool, but there’s a lot of quirks and tricks that makes you lose a lot of time to make it actually 'usable'. Not only does babun solve most of these problems, but also contains a lot of vital packages, so that you can be productive from the very first minute.
### Package Manager
Babun provides a package manager called ```pact```. It is similar to 'apt-get' or 'yum'. Pact enables installing/searching/upgrading and deinstalling cygwin packages with no hassle at all. Just invoke ```pact --help``` to check how to use it.
### Shell
Babun’s shell is tweaked in order to provide the best possible user-experience. There are two shell types that are pre-configured and available right away - bash and zsh (zsh is the default one). Babun’s shell features:

* syntax highlighting

* UNIX tools

* software development tools

* git-aware prompt

* custom scripts and aliases

and more!

### Console
Mintty is the console used in babun. It features an ```xterm-256 mode```, nice fonts and simply looks great!
### Proxying
Babun supports HTTP proxying out of the box. Just add the address and the credentials of your HTTP proxy server to the ```.babunrc``` file located in your home folder and execute ```source .babunrc``` to enable HTTP proxying. SOCKS proxies are not supported for now.
### Developer tools
Babun provides many packages, convenience tools and scripts that make your life much easier. The long list of features includes:

* programming languages (Python, Perl, etc.)

* git (with a wide variety of aliases and tweaks)

* UNIX tools (grep, wget, curl, etc.)

* vcs (svn, git)

* oh-my-zsh

* custom scripts (pbcopy, pbpaste, babun, etc.)
### Plugin architecture
Babun has a very small microkernel (cygwin, a couple of bash scripts and a bit of a convention) and a plugin architecture on the top of it. It means that almost everything is a plugin in the babun’s world! Not only does it structure babun in a clean way, but also enables others to contribute small chunks of code. Currently, babun comprises the following plugins:

* cacert

* core

* git

* oh-my-zsh

* pact

* cygdrive

* dist

* shell
### Auto-update
Self-update is at the very heart of babun! Many Cygwin tools are simple bash scripts - once you install them there is no chance of getting the newer version in a smooth way. You either delete the older version or overwrite it with the newest one losing all the changes you have made in between.

Babun contains an auto-update feature which enables updating both the microkernel, the plugins and even the underlying cygwin. Files located in your home folder will never be deleted nor overwritten which preserves your local config and customizations.
### Installer
Babun features an silent command-line installation script that may be executed without admin rights on any Windows hosts.
## Using babun
### Setting up proxy
To setup proxy uncomment following lines in the ```.babunrc``` file ```(%USER_HOME%\.babun\cygwin\home\USER\.babunrc)```
```Uncomment this lines to set up your proxy
# export http_proxy=http://user:password@server:port
# export https_proxy=$http_proxy
# export ftp_proxy=$http_proxy
# export no_proxy=localhost
```
### Setting up git
Babun has a pre-configured git. The only thing you should do after the installation is to add your name and email to the git config:
```git config --global user.name "your name"```

```git config --global user.email "your@email.com"```
