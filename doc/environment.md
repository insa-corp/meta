# Environment configuration

Here is a small tutorial to set up the full environment required to develop on our projects.

Cross-platform:

 * [Git](#git)
 * [Node.js (4.x)](#nodejs)
 * [npm (2.x)](#npm)
 * python (2.7)
 * [MongoDB (3.x) _(optionnal)_](#mongodb)
 * [Ruby (2.x)](#ruby)
 * [Sass](#sass)

Windows:

 * Visual Studio C++ (2013 or above) _(optionnal ?)_

Unix:

 * make
 * gcc

## Terminal

Some steps require you to use the terminal. Here is a quick reminder about how to access the terminal.

Terminal commands will be displayed as follow:

````
path $ command --options
````

`path` indicates the path of the current directory, you do not have to type it. When the path is not explicitly defined, it is assumed to be any path or the project root according to the context.
`$` indicates the command prompt, you do not have to type it either.

### Windows

You can open a terminal in any directory from the `shift + right click` context menu (`Open command window here`).

When adding variables to the `PATH`, you will have to open a new terminal in order get the updated value.

### Linux

Linux heavily relies on the terminal but if you're still unsure about how to access it, check your distribution's or desktop environment's help.

## Git

### Description

Git is the [Version Control System (VCS)](https://en.wikipedia.org/wiki/Version_control) used accross all our projects.
It helps us to manage our project: download sources, track history, push revisions, etc.

### Installation

[Follow the instructions from git's website](https://git-scm.com/)

#### Windows (`v2.7.0`)

##### Components

 * Uncheck `Explorer integration`
 * Check `Associate .git* configurations file with the default editor`
 * Check `Associate .sh files to be run with Bash`
 
##### Adjusting the PATH environment

`Use Git from the Windows Command Prompt.`

##### Line endings conversion

`Checkout Windows-style, commit Unix-style line-endings.`

### Configuration

````
$ git config --global user.name "Your Name"
$ git config --global user.email "youremail@example.com"
````

### Check installation

`$ git --version`

## Node.js

### Description

[Node.js](https://nodejs.org/en/) (or `node` for short) is a JavaScript Virtual Machine.
We use it to build our projects and run server code.
It also comes with `npm`, a package manager for Node modules.

### Installation

[Download page](https://nodejs.org/en/download/)

Make sure to install `npm` with it and add both `node` & `npm` to your `PATH`.

### Check installation

`$ node --version`

## npm

### Installation

See Node.js.

### Check installation

`$ npm --version`

## MongoDB

### Description

Document oriented DB.

### Installation

[Download link](https://www.mongodb.org/)

## Ruby

Install the ruby langage compiler. It is required for Sass.

### Installation


### Windows 

Download the installer for the latest version (currently 2.2.4 or 2.2.4 (x64)) from the [Ruby Installer project](http://rubyinstaller.org/downloads/).

Run it as administrator.

You can change the location to not use the root of your computer (ie. `C:\Program Files\Ruby22`). Make sure to check `Add Ruby executable to your PATH`. Optionnaly, associate files.

__Warning__: It seems that the current version of Ruby's `gem` has a small issue when the location contains spaces. A ticket is openned for this issue on Github but there is a quick workaround if you are stuck. ([see Sass](#sass))

### Check installation

````bash
$ ruby --version
$ gem --version
````

## Sass

Modern language for stylesheets: powerful syntax and stylesheet imports from third party.

### Installation

Make sure you have Ruby (with Gem), then simple execute `$ gem install sass`. (You may have to start a terminal with administrator privileges).

__Fixing__ the script if there spaces in the path of your Ruby directory:

Edit the file `RUBY_HOME $ bin/sass.bat` by removing the superfluous double quotes. Here is what you should get:
````bat
@ECHO OFF
IF NOT "%~f0" == "~f0" GOTO :WinNT
@"C:\Program Files\Ruby22\bin\ruby.exe" "C:/Program Files/Ruby22/bin/sass" %1 %2 %3 %4 %5 %6 %7 %8 %9
GOTO :EOF
:WinNT
@"C:\Program Files\Ruby22\bin\ruby.exe" "%~dpn0" %*
````

### Check installation

````bash
$ sass --version
````

## Java SDK

### Description

Required by the Android SDK

### Installation (1.8)

[Download link](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

## Android SDK

### Description

Required by `nativescript` to build Android applications.

### Installation

[Download link](http://developer.android.com/sdk/index.html)

(SDK Tools Only)

````
android-home $ tools/android sdk
````

Install Android 6.0 (SDK)

````
android-home $ tools/android avd
````

Create new Android Virtual Device.
