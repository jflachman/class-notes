---
created: 2024-02-21T22:58:05 (UTC -07:00)
tags: []
source: chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html
author: craigloewen-msft
---

# 

> ## Excerpt
> Install Windows Subsystem for Linux with the command, wsl --install. Use a Bash terminal on your Windows machine run by your preferred Linux distribution - Ubuntu, Debian, SUSE, Kali, Fedora, Pengwin, Alpine, and more are available.

---
## How to install Linux on Windows with WSL

-   Article
-   08/28/2023

## In this article

1.  [Prerequisites](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#prerequisites)
2.  [Install WSL command](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#install-wsl-command)
3.  [Change the default Linux distribution installed](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#change-the-default-linux-distribution-installed)
4.  [Set up your Linux user info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#set-up-your-linux-user-info)

Developers can access the power of both Windows and Linux at the same time on a Windows machine. The Windows Subsystem for Linux (WSL) lets developers install a Linux distribution (such as Ubuntu, OpenSUSE, Kali, Debian, Arch Linux, etc) and use Linux applications, utilities, and Bash command-line tools directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#prerequisites)

## Prerequisites

You must be running Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11 to use the commands below. If you are on earlier versions please see [the manual install page](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/install-manual).

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#install-wsl-command)

## Install WSL command

You can now install everything you need to run WSL with a single command. Open PowerShell or Windows Command Prompt in **administrator** mode by right-clicking and selecting "Run as administrator", enter the wsl --install command, then restart your machine.

```
<span>wsl<span> --install</span>
</span>
```

This command will enable the features necessary to run WSL and install the Ubuntu distribution of Linux. ([This default distribution can be changed](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/basic-commands#install)).

If you're running an older build, or just prefer not to use the install command and would like step-by-step directions, see **[WSL manual installation steps for older versions](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/install-manual)**.

The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for files to de-compress and be stored on your machine. All future launches should take less than a second.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#change-the-default-linux-distribution-installed)

## Change the default Linux distribution installed

By default, the installed Linux distribution will be Ubuntu. This can be changed using the `-d` flag.

-   To change the distribution installed, enter: `wsl --install -d <Distribution Name>`. Replace `<Distribution Name>` with the name of the distribution you would like to install.
-   To see a list of available Linux distributions available for download through the online store, enter: `wsl --list --online` or `wsl -l -o`.
-   To install additional Linux distributions after the initial install, you may also use the command: `wsl --install -d <Distribution Name>`.

Tip

If you want to install additional distributions from inside a Linux/Bash command line (rather than from PowerShell or Command Prompt), you must use .exe in the command: `wsl.exe --install -d <Distribution Name>` or to list available distributions: `wsl.exe -l -o`.

If you run into an issue during the install process, check the [installation section of the troubleshooting guide](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/troubleshooting#installation-issues).

To install a Linux distribution that is not listed as available, you can [import any Linux distribution](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/wsl/use-custom-distro) using a TAR file. Or in some cases, [as with Arch Linux](https://wsldl-pg.github.io/ArchW-docs/How-to-Setup/), you can install using an `.appx` file. You can also create your own [custom Linux distribution](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/wsl/build-custom-distro) to use with WSL.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#set-up-your-linux-user-info)

## Set up your Linux user info

Once you have installed WSL, you will need to create a user account and password for your newly installed Linux distribution. See the [Best practices for setting up a WSL development environment](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/setup/environment#set-up-your-linux-username-and-password) guide to learn more.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#set-up-and-best-practices)

## Set up and best practices

We recommend following our [Best practices for setting up a WSL development environment](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/setup/environment) guide for a step-by-step walk-through of how to set up a user name and password for your installed Linux distribution(s), using basic WSL commands, installing and customizing Windows Terminal, set up for Git version control, code editing and debugging using the VS Code remote server, good practices for file storage, setting up a database, mounting an external drive, setting up GPU acceleration, and more.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#check-which-version-of-wsl-you-are-running)

## Check which version of WSL you are running

You can list your installed Linux distributions and check the version of WSL each is set to by entering the command: `wsl -l -v` in PowerShell or Windows Command Prompt.

To set the default version to WSL 1 or WSL 2 when a new Linux distribution is installed, use the command: `wsl --set-default-version <Version#>`, replacing `<Version#>` with either 1 or 2.

To set the default Linux distribution used with the `wsl` command, enter: `wsl -s <DistributionName>` or `wsl --set-default <DistributionName>`, replacing `<DistributionName>` with the name of the Linux distribution you would like to use. For example, from PowerShell/CMD, enter: `wsl -s Debian` to set the default distribution to Debian. Now running `wsl npm init` from Powershell will run the `npm init` command in Debian.

To run a specific wsl distribution from within PowerShell or Windows Command Prompt without changing your default distribution, use the command: `wsl -d <DistributionName>`, replacing `<DistributionName>` with the name of the distribution you want to use.

Learn more in the guide to [Basic commands for WSL](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/basic-commands).

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#upgrade-version-from-wsl-1-to-wsl-2)

## Upgrade version from WSL 1 to WSL 2

New Linux installations, installed using the `wsl --install` command, will be set to WSL 2 by default.

The `wsl --set-version` command can be used to downgrade from WSL 2 to WSL 1 or to update previously installed Linux distributions from WSL 1 to WSL 2.

To see whether your Linux distribution is set to WSL 1 or WSL 2, use the command: `wsl -l -v`.

To change versions, use the command: `wsl --set-version <distro name> 2` replacing `<distro name>` with the name of the Linux distribution that you want to update. For example, `wsl --set-version Ubuntu-20.04 2` will set your Ubuntu 20.04 distribution to use WSL 2.

If you manually installed WSL prior to the `wsl --install` command being available, you may also need to [enable the virtual machine optional component](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/install-manual#step-3---enable-virtual-machine-feature) used by WSL 2 and [install the kernel package](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/install-manual#step-4---download-the-linux-kernel-update-package) if you haven't already done so.

To learn more, see the [Command reference for WSL](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/basic-commands) for a list of WSL commands, [Comparing WSL 1 and WSL 2](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/compare-versions) for guidance on which to use for your work scenario, or [Best practices for setting up a WSL development environment](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/setup/environment) for general guidance on setting up a good development workflow with WSL.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#ways-to-run-multiple-linux-distributions-with-wsl)

## Ways to run multiple Linux distributions with WSL

WSL supports running as many different Linux distributions as you would like to install. This can include choosing distributions from the [Microsoft Store](https://aka.ms/wslstore), [importing a custom distribution](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/use-custom-distro), or [building your own custom distribution](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/build-custom-distro).

There are several ways to run your Linux distributions once installed:

-   [Install Windows Terminal](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/terminal/get-started) _**(Recommended)**_ Using Windows Terminal supports as many command lines as you would like to install and enables you to open them in multiple tabs or window panes and quickly switch between multiple Linux distributions or other command lines (PowerShell, Command Prompt, Azure CLI, etc). You can fully customize your terminal with unique color schemes, font styles, sizes, background images, and custom keyboard shortcuts. [Learn more.](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/terminal)
-   You can directly open your Linux distribution by visiting the Windows Start menu and typing the name of your installed distributions. For example: "Ubuntu". This will open Ubuntu in its own console window.
-   From Windows Command Prompt or PowerShell, you can enter the name of your installed distribution. For example: `ubuntu`
-   From Windows Command Prompt or PowerShell, you can open your default Linux distribution inside your current command line, by entering: `wsl.exe`.
-   From Windows Command Prompt or PowerShell, you can use your default Linux distribution inside your current command line, without entering a new one, by entering:`wsl [command]`. Replacing `[command]` with a WSL command, such as: `wsl -l -v` to list installed distributions or `wsl pwd` to see where the current directory path is mounted in wsl. From PowerShell, the command `get-date` will provide the date from the Windows file system and `wsl date` will provide the date from the Linux file system.

The method you select should depend on what you're doing. If you've opened a WSL command line within a Windows Prompt or PowerShell window and want to exit, enter the command: `exit`.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#want-to-try-the-latest-wsl-preview-features)

## Want to try the latest WSL preview features?

Try the most recent features or updates to WSL by joining the [Windows Insiders Program](https://insider.windows.com/getting-started). Once you have joined Windows Insiders, you can choose the channel you would like to receive preview builds from inside the Windows settings menu to automatically receive any WSL updates or preview features associated with that build. You can choose from:

-   Dev channel: Most recent updates, but low stability.
-   Beta channel: Ideal for early adopters, more reliable builds than the Dev channel.
-   Release Preview channel: Preview fixes and key features on the next version of Windows just before its available to the general public.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#additional-resources)

## Additional resources

-   [Windows Command Line Blog: Install WSL with a single command now available in Windows 10 version 2004 and higher](https://devblogs.microsoft.com/commandline/install-wsl-with-a-single-command-now-available-in-windows-10-version-2004-and-higher/)

Collaborate with us on GitHub

The source for this content can be found on GitHub, where you can also create and review issues and pull requests. For more information, see [our contributor guide](https://learn.microsoft.com/contribute/content/how-to-write-quick-edits).

## Additional resources

___

Training

___

Documentation

-   [Comparing WSL Versions](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/wsl/compare-versions?source=recommendations)
    
    WSL 2 provides the benefits of WSL 1, but uses an actual Linux kernel, rather than a translation layer like WSL 1, resulting in faster performance.
    
-   [Troubleshooting Windows Subsystem for Linux](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/wsl/troubleshooting?source=recommendations)
    
    Provides detailed information about common errors and issues people run into while running Linux on the Windows Subsystem for Linux.
    
-   [Basic commands for WSL](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/en-us/windows/wsl/basic-commands?source=recommendations)
    
    Reference for the basic commands included with Windows Subsystem for Linux (WSL).
