---
layout: page
title: Installation
---

> It is easiest to install Git on Linux using the preferred package manager of your Linux distribution.

&nbsp;

## ✰ Debian/Ubuntu

***

* For the latest stable version for your release of Debian/Ubuntu

   ```sh
   apt-get install git
   ```

* For Ubuntu, this PPA provides the latest stable upstream Git version

   ```sh
   add-apt-repository ppa:git-core/ppa

   apt update

   apt install git
   ```

&nbsp;

## ✰ Customize Git Environment

***

  > Git provides the git config tool, which allows you to set configuration variables. Git stores all global configurations in `.gitconfig` file, which is located in your `home` directory. To set these configuration values as global, add the `--global` option, and if you omit --global option, then your configurations are specific for the current Git repository.

***

  >You can also set up system wide configuration. Git stores these values in the `/etc/gitconfig` file, which contains the configuration for every user and repository on the system. To set these values, you must have the root rights and use the `--system` option.

* Setting username

  >This information is used by Git for each commit.

    ```sh
    git config --global user.name "username"
    ```

* Setting email id

  >This information is used by Git for each commit.

    ```sh
    git config --global user.email "user@gmail.com"
    ```

* Avoid merge commits for pulling

  > You pull the latest changes from a remote repository, and if these changes are divergent, then by default Git creates merge commits. We can avoid this via following settings.

    ```sh
    git config --global branch.autosetuprebase always
    ```

* Color highlighting

  > The following commands enable color highlighting for Git in the console.

    ```sh
    git config --global color.ui true

    git config --global color.status auto

    git config --global color.branch auto
    ```

* Setting default editor

  > By default, Git uses the system default editor, which is taken from the VISUAL or EDITOR environment variable. We can configure a different one by using git config.

    ```sh
    git config --global core.editor vscode
    ```

* Setting default merge tool

  > Git does not provide a default merge tool for integrating conflicting changes into your working tree. We can set default merge tool by enabling following settings.

    ```sh
    git config --global merge.tool meld
    ```

* Listing Git settings

  > To verify your Git settings of the local repository, use git config –list command as given below.

    ```sh
    git config --list
    ```