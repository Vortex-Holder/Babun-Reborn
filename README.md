# Babun - The Reborn of a Good Terminal [PROJECT DISABLED]
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

There’s a lot of great git aliases provided by the git plugin:

```gitalias['alias.cp']='cherry-pick'
gitalias['alias.st']='status -sb'
gitalias['alias.cl']='clone'
gitalias['alias.ci']='commit'
gitalias['alias.co']='checkout'
gitalias['alias.br']='branch'
gitalias['alias.dc']='diff --cached'
gitalias['alias.lg']="log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %Cblue<%an>%Creset' --abbrev-commit --date=relative --all"
gitalias['alias.last']='log -1 --stat'
gitalias['alias.unstage']='reset HEAD --'
```
### Installing and removing packages
Babun is shipped with ```pact``` - a Linux like package manager. It uses the cygwin repository for downloading packages:

```{ ~ } » pact install arj                                                                     ~
Working directory is /setup
Mirror is http://mirrors.kernel.org/sourceware/cygwin/
setup.ini taken from the cache

Installing arj
Found package arj
--2014-03-30 19:34:38--  http://mirrors.kernel.org/sourceware/cygwin//x86/release/arj/arj-3.10.22-1.tar.bz2
Resolving mirrors.kernel.org (mirrors.kernel.org)... 149.20.20.135, 149.20.4.71, 2001:4f8:1:10:0:1994:3:14, ...
Connecting to mirrors.kernel.org (mirrors.kernel.org)|149.20.20.135|:80... connected.
HTTP request sent, awaiting response... 200 OK
Length: 189944 (185K) [application/x-bzip2]
Saving to: `arj-3.10.22-1.tar.bz2'

100%[=======================================>] 189,944      193K/s   in 1.0s

2014-03-30 19:34:39 (193 KB/s) - `arj-3.10.22-1.tar.bz2' saved [189944/189944]

Unpacking...
Package arj installed
```
Here’s the list of all pact’s features:

```{ ~ }  » pact --help
pact: Installs and removes Cygwin packages.

Usage:
  "pact install <package names>" to install given packages
  "pact remove <package names>" to remove given packages
  "pact update <package names>" to update given packages
  "pact show" to show installed packages
  "pact find <patterns>" to find packages matching patterns
  "pact describe <patterns>" to describe packages matching patterns
  "pact packageof <commands or files>" to locate parent packages
  "pact invalidate" to invalidate pact caches (setup.ini, etc.)
Options:
  --mirror, -m <url> : set mirror
  --invalidate, -i       : invalidates pact caches (setup.ini, etc.)
  --force, -f : force the execution
  --help
  --version
```
### Changing the default shell
The zsh (with .oh-my-zsh) is the default babun’s shell.

Executing the following command will output your default shell:

```{ ~ } » babun shell```
```/bin/zsh```

In order to change your default shell execute:

```{ ~ } » babun shell /bin/bash```
```/bin/zsh```
```/bin/bash```

The output contains two lines: the previous default shell and the new default shell

### Checking the configuration
Execute the following command the check the configuration:

```{ ~ }  » babun check                                                                         ~
Executing babun check
Prompt speed      [OK]
Connection check  [OK]
Update check      [OK]
Cygwin check      [OK]
```
By executing this command you can also check whether there is a newer cygwin version available:

```{ ~ }  » babun check                                                                            ~
Executing babun check
Prompt speed      [OK]
Connection check  [OK]
Update check      [OK]
Cygwin check      [OUTDATED]
Hint: the underlying Cygwin kernel is outdated. Execute 'babun update' and follow the instructions!
```
It will check if there are problems with the speed of the git prompt, if there’s access to the Internet or finally if you are running the newest version of babun.

The command will output hints if problems occur:

```{ ~ } » babun check                                                                          ~
Executing babun check
Prompt speed      [SLOW]
Hint: your prompt is very slow. Check the installed 'BLODA' software.
Connection check  [OK]
Update check      [OK]
Cygwin check      [OK]
```
On each startup, but only every 24 hours, babun will execute this check automatically. You can disable the automatic check in the ~/.babunrc file.
### Tweaking the configuration
You can tweak some config options in the ~/.babunrc file. Here’s the full list of variables that may be modified:

```# JVM options
export JAVA_OPTS="-Xms128m -Xmx256m"

# Modify these lines to set your locale
export LANG="en_US.UTF-8"
export LC_CTYPE="en_US.UTF-8"
export LC_ALL="en_US.UTF-8"

# Uncomment these lines to the set your machine's default locale (and comment out the UTF-8 ones)
# export LANG=$(locale -uU)
# export LC_CTYPE=$(locale -uU)
# export LC_ALL=$(locale -uU)

# Uncomment this to disable daily auto-update & proxy checks on startup (not recommended!)
# export DISABLE_CHECK_ON_STARTUP="true"

# Uncomment to increase/decrease the check connection timeout
# export CHECK_TIMEOUT_IN_SECS=4

# Uncomment this lines to set up your proxy
# export http_proxy=http://user:password@server:port
# export https_proxy=$http_proxy
# export ftp_proxy=$http_proxy
# export no_proxy=localhost
```
### Updating babun
To update babun to the newest version execute:

```babun update```


Please note that your local configuration files will not be overwritten.

The 'babun update' command will also update the underlying cygwin version if never version is available. In such case babun will download the new cygwin installer, close itself and start the cygwin installation process. Once cygwin installation is completed babun will restart.

## Screenshots
Startup Screen
<img width="827" height="488" alt="screen_welcome" src="https://github.com/user-attachments/assets/50adfb04-e809-4d36-925d-a1e9aef72501" />
Pact - package installation
<img width="827" height="487" alt="screen_pact_install" src="https://github.com/user-attachments/assets/6b6eb8ab-109e-4208-9f1a-4938a996c526" />
Pact - package installed
<img width="832" height="489" alt="screen_pact_installed" src="https://github.com/user-attachments/assets/0dcdee73-bbe3-4e77-a622-adf956d2471c" />
Babun oh-my-zsh - auto-update
<img width="770" height="549" alt="screen_zsh_update" src="https://github.com/user-attachments/assets/6cc59c78-13d0-451d-af25-38c19f538b57" />
VIM syntax highlighting
<img width="827" height="484" alt="screen_vim" src="https://github.com/user-attachments/assets/c9f43633-4012-45c7-beda-ad974be0f354" />
Nano syntax highlighting
<img width="829" height="486" alt="screen_nano" src="https://github.com/user-attachments/assets/6acc8186-0fe8-4256-bee1-848706d17da1" />
Git aliases - git lg
<img width="828" height="489" alt="screen_git_lg" src="https://github.com/user-attachments/assets/48c274dc-efe7-4db6-ad03-ab86a92723e1" />
Git aliases - git st
<img width="828" height="488" alt="screen_git_st" src="https://github.com/user-attachments/assets/1b69951a-1880-41c5-9fea-4ac87a52b320" />
Shell prompt
<img width="825" height="488" alt="screen_shell" src="https://github.com/user-attachments/assets/32ed2294-ceeb-47dd-a9b6-b88aff10290d" />
Babun update
<img width="826" height="486" alt="screen_update" src="https://github.com/user-attachments/assets/59c0290b-dc4c-47e8-a0d1-edd0943ab182" />
Open Babun here - Context Menu
<img width="625" height="155" alt="screen_context_menu" src="https://github.com/user-attachments/assets/19ffa16f-c6e4-42aa-b460-894cde38dfa6" />
## Development
Babun is back! New name is Babun Reborn.

Have fun :D
