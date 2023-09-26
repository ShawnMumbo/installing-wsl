# WSL INSTALLATION AND CONFIGURAION WITH ELIXIR ERLANG
### Introduction

This blog is to aid in getting the VS code debugger with the following features:
  - Debugger support
  - Automatic, incremental Dialyzer analysis
  - Automatic inline suggestion of @specs based on Dialyzer's inferred success typings
  - Inline reporting of build warnings and errors
  - Documentation lookup on hover
  - Go-to-definition
  - Code completion
  - Code formatter
  - Find references to functions and modules (Thanks to @mattbaker)
  - Quick symbol lookup in file (Thanks to @mattbaker)
  - Quick symbol lookup in workspace and stdlib (both Elixir and erlang) (@lukaszsamson)

### Configuring WSL with Elixir

VS-Code Setup for WSL
For a more in depth guide on how to configure WSL on VS-Code click on the link [here](https://code.visualstudio.com/docs/remote/wsl).

To use WSL on vs code and link to elixir three plug-ins are needed.

There is two ways to use WLS in VS-Code;

1. Using WSL-Windows side -> to use this,
      - Open Vs-Code
      - Install WSL Plugin
      - Install ElixirLs Plugin 
      - Restart the computer, start a WSL mix project or open terminal and run elixir commands to verify

2. Using WSL-Ubuntu -> This will use WSL but under Linux distribution, to do this;
      - Open VS-Code
      - Install WSL-Remote 
      - Click on the " ><" symbol on the bottom left of your VS-Code window, and click on "Connect to WSL using Distro"
      - Then Search for ElixirLs Plugin and click on "Install in WSL"
      - Restart your Computer and VS-Code and run a mix project or Open Terminal from VS-Code and try a few elixir commands.
      - Your GitHub should be picked up from Windows auth side.

## Windows Option

The latest version as of Erlang and Elixir as of 26/09/2023 is [Erlang/OTP 26.0.2](https://github.com/erlang/otp/releases/download/OTP-26.0.2/otp_win64_26.0.2.exe) and Elixir is [Elixir 1.15.4](https://github.com/elixir-lang/elixir/releases/download/v1.15.4/elixir-otp-26.exe) respectively. 
When using the Visual Studio Code plugin for Elixir called [ElixirLS](https://elixir-lsp.github.io/elixir-ls/), support is Limited.
See the table below for support.  Read more about ElixirLS Github Repo [here](https://github.com/elixir-lsp/elixir-ls).

## Into WSL

# Windows Subsystem Linux 
    by Shawn Mumbo
## BIOS



## Windows

## On the windows search bar, Open windows features turn on and off, turn on Windows subsystem for linux and virtual machine options.
## Open Powershell and run as admin

    1.wsl --install
    2.wsl --status

   Confirm it is wsl-2
   Click here for [WSL Documentation](https://learn.microsoft.com/en-us/windows/wsl/)

## Linux Terminal

### Ubuntu commands to check linux version, confirm linux installation and install git using curl to enable data transfer over various network protocols. 

    Open UBUNTU as admin
      3.pwd
      4.lsb_release -a 
      5.sudo apt install curl git
## Package Handler:

### This installs asdf package handler. 

    6.git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.12.0     
    7.echo ". $HOME/.asdf/asdf.sh" >> ~/.bashrc     
    8.source ~/.bashrc
    9.asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git\
Click here for [asdf Documentation](https://asdf-vm.com/guide/introduction.html)
    
### Dependencies and Plugins:
       10.sudo apt-get update
       11.sudo apt-get install libssl-dev
       12.sudo apt-get install autoconf
       13.sudo apt-get install libncurses5-dev
       14.sudo apt-get install fop
       15.sudo apt install python3 g++ make python3-pip
       16.sudo apt-get install xsltproc
       17.sudo apt-get install unixodbc-dev
       18.sudo apt install libxml2-utils
       19.sudo apt install default-jdk
       20.sudo apt-get install erlang-jinterface
       21.sudo apt install inotify-tools libtool automake libgmp-dev make libwxgtk-webview3.0-gtk3-dev libssl-dev libncurses5-dev curl git 
       22.sudo apt install libjpeg-dev libpng-dev libtiff-dev zlib1g-dev libncurses5-dev libssh-dev unixodbc-dev libgmp3-dev libwxbase3.0-dev libwxgtk3.0-gtk3-dev libwxgtk-webview3.0-gtk3-dev libsctp-dev lksctp-tools build-essential libgtk-3-dev libnotify-dev libsecret-1-dev catch
       23.sudo apt install libwxgtk-webview3.0-gtk3-dev
Click here for [Linux Package Install Documentation](https://howtoinstall.co/en/)
And search the specified command for explanation.
      
      
   Plugins:
### We Install node Js to check if asdf is working as a package installer
    
        24.asdf install nodejs latest    
        25.asdf local nodejs latest    
        26.asdf global nodejs latest

        
### We Install elixir and erlang plugins 

        
        27.asdf plugin add erlang    
        28.asdf plugin add elixir

### We check for the latest version of erlang and elixir supported by ElixirLs plugin and install
##### The update on support can be found in the link here [Elixir ls Documentation](https://github.com/elixir-lsp/elixir-ls)

        29.asdf list-all erlang
        30.KERL_BUILD_DOCS=yes asdf install erlang 25.3.2.3

##### Make sure to download the OTP distributions and not the regular.

        31.asdf list-all elixir
        32.asdf install elixir 1.15.0-otp-25    

### Setting the local and global user environments to be able to work with third party apps and plugins

        33.asdf local elixir 1.15.0-otp-25    
        34.asdf global elixir 1.15.0-otp-25
        35.asdf local erlang 25.3.2.3  
        36.asdf global erlang 25.3.2.3

### Check if Elixir has been installed properly, should return your Elixir version number

 
        37.elixir -v



# FAQ's

Question - Do you need to uninstall Elixir on Windows side if I Install WSL?
Answer - No, They can work Independently.

Question - What is the use of Installing the Python and Java Libraries?
Answer - Python- Python is installed as a dependency to elixir to overcome Elixir's limitations when 	dealing with big mathematical problems. - for example when it comes to longer calculations,including matrixes or some kind of optimization. It is surprising that in Elixir, according to José 	Valim’s post, the problem is not the mathematical processing, but rather the lack of support for large, mutable structures. Due to the immutable nature of data in Elixir, you really need a lot of copying of immutable structures to perform a simple matrix operation.
Java - This helps Elixir run Java file and projects and acts as a dependency.

Question - Where do I download my VS-Code and other apps and/or software.
Answer - Depending on the App or software versions needed and support available, you could use either/or.
Applications like pgAdmin, VS - Code and  Xlaunch can access file systems on both WSL and ubuntu, so for ease-of-use, it is recommended to just use the Windows installation. 
Application managers like asdf need to be installed in Linux, databases like PostgreSQL depends on the file location of your project, make sure they are in similar environments as the project. 


