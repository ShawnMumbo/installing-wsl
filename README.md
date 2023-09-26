# WSL INSTALLATION AND CONFIGURAION WITH ELIXIR ERLANG
## Introduction

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

## Configuring WSL with Elixir

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
