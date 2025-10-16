---
title: Setup
---

::::::::::::::::::::::::::::::::::::::::::  prereq

## Minimum requirements

Completing this course requires:

- Access to a computer with Git installed
- A [GitHub](https://github.com) account
- A configured `recipe` repository
- Be comfortable with using Git

This course is currently being delivered in
person and remotely so please make sure you have access to a suitable computer.


::::::::::::::::::::::::::::::::::::::::::::::::::

## Configure your `recipe` repository

If you **have** completed our [Introduction to using Git and GitHub for software
development][intro-course] course, you should have a `recipe` repository in your
GitHub account that will be used in this course. Specifically, in the lesson on
[Committing and History][commit-history] from the Introduction course, we discuss
how to set up the `recipe` repository. Make sure you have a clone of that repo in
your local home directory.

If you **have not** completed the intro course:

- Download [this zip archive](code/recipe_with_history.zip) that contains the `recipe`
  repo with some previous commit history that will be used in the session.
- Extract it into your home directory.
- [Create a repository][commit-history] on your personal GitHub account and set it as the remote for this
  `recipe` repository you have locally.

:::::::::::::::::::::::::::::::::::::::::  callout

## Important

If you do not know how to set up a remote repo on GitHub, you can follow the steps in
the "Configuring a remote repository from a local one" exercise in [this lesson from
intro course][remote-repo-lesson]


::::::::::::::::::::::::::::::::::::::::::::::::::

## Install Git

:::::::::::::::::::::::::::::::::::::::::  callout

## Important

If you do not already have Git installed or are not comfortable with using it for
simple version control tasks, you should consider attending our
[Introduction to using Git and GitHub for software development][intro-course] course
first.


::::::::::::::::::::::::::::::::::::::::::::::::::

Please follow the relevant instructions depending on your operating system.

:::::::::::::::  solution

## Windows

1. Download the Git for Windows [installer](https://git-for-windows.github.io/).
2. Run the installer and follow the steps below:
  1. Click on "Next" four times (two times if you've previously installed Git). You don't need to change anything in the Information, location, components, and start menu screens.
  2. From the dropdown menu select "Use the nano editor by default" and click on "Next".
  3. Select "Override the default branch name for new repositories" and use inclusive terms like "main" (Refer: [The new Git default branch name](https://about.gitlab.com/blog/2021/03/10/new-git-default-branch-name/))
  4. Ensure that "Git from the command line and also from 3rd-party software" is selected and click on "Next". (If you don't do this Git Bash will not work properly, requiring you to remove the Git Bash installation, re-run the installer and to select the "Git from the command line and also from 3rd-party software" option.)
  5. Ensure that "Use bundled OpenSSH" is selected and click on "Next".
  6. Ensure that "Use the native Windows Secure Channel library" is selected and click on "Next".
  7. Ensure that "Checkout Windows-style, commit Unix-style line endings" is selected and click on "Next".
  8. Ensure that "Use Windows' default console window" is selected and click on "Next".
  9. Ensure that "Fast-forward or merge" is selected and click on "Next".
  10. Ensure that "Git Credential Manager" is selected and click on "Next".
  11. Ensure that "Enable file system caching" is selected and click on "Next".
  12. Ensure to select "Enable experimental built-in file system monitor" and click on "Install".
  13. Click on "Finish".
3. If your "HOME" environment variable is not set (or you don't know what this is):
  1. Open command prompt (Open Start Menu then type `cmd` and press [Enter])
  2. Type the following line into the command prompt window exactly as shown: `setx HOME "%USERPROFILE%"`
  3. Press [Enter], you should see `SUCCESS: Specified value was saved`.
  4. Quit command prompt by typing `exit` then pressing [Enter]

This will provide you with both Git and Bash via the program Git Bash. You
should be able to launch Git Bash from the Start Menu. Within the window that
launches enter the command `git --version` and press enter. You should see
output similar to that below:

```output
git version 2.40.0.windows-1
```

:::::::::::::::::::::::::

:::::::::::::::  solution

## macOS

Apple provide a suite of UNIX-style command line tools that includes git. Install
them by opening the "Terminal" app and running:

```commands, bash
xcode-select --install
```

```output
xcode-select: note: install requested for command line developer tools
```

This will open a dialog that asks for your confirmation to install the tools. If
it does not open a dialog, it may be because it is already installed (the error
message will be clear).

To check the installation was successful, run the command:

```commands, bash
git --version
```

You should see output similar to that below:

```output
git version 2.37.1 (Apple Git-137.1)
```

**If the above does not work**, you may have and older version of macOS.
Try the following: install Git for Mac by downloading and running the
most recent "mavericks" installer from [this list][installer-list]. Because this
installer is not signed by the developer, you may have to right click (control
click) on the .pkg file, click Open, and click Open on the pop up window. After
installing Git, there will not be anything in your `/Applications` folder, as
Git is a command line program. **For older versions of OS X (10.5-10.8)** use
the most recent available installer labelled "snow-leopard".


:::::::::::::::::::::::::

:::::::::::::::  solution

## Linux

If Git is not already available on your machine you can try to install it via
your distribution's package manager.

For **Debian/Ubuntu** run:

```commands, bash
sudo apt-get install git
```

For **Fedora** run:

```commands, bash
sudo dnf install git
```

To check the installation was successful open a new terminal. In the window that
launches enter the command:

```commands, bash
git --version
```

You should see output similar to that below:

```output
git version 2.40.0
```

:::::::::::::::::::::::::

## Configure Git to use your preferred text editor

Many Git commands require you to provide input via a text editor (though you can often skip this step with additional command-line arguments). For example, running `git commit` by itself will open a text editor to allow you to enter a commit message. Depending on your OS and how you installed Git, the text editor Git will use can be any number of things, but is likely to be either [nano] or [vim], which are both terminal-based editors. It is best to configure your preferred editor explicitly (if you are using editor for the first time, it is advisable to use nano).

To view the currently configured text editor, you can run:

```commands, bash
git config --global core.editor
```

(The output may be empty, indicating that no editor has been selected.)

If you would prefer to use a graphical text editor, there is [useful documentation on GitHub] on how to do this for some common editors.

If you would rather just use nano, you can run:

```commands, bash
git config --global core.editor nano
```

<!-- markdown-link-check-disable-next-line -->



[intro-course]: https://imperialcollegelondon.github.io/rse_introductory_git_course/
[commit-history]: https://imperialcollegelondon.github.io/rse_introductory_git_course/l1-02-committing-history/index.html
[remote-repo-lesson]: https://imperialcollegelondon.github.io/rse_introductory_git_course/l2-02-remote_repositories/index.html
[installer-list]: https://sourceforge.net/projects/git-osx-installer/files/
[nano]: https://www.nano-editor.org
[vim]: https://www.vim.org
[useful documentation on GitHub]: https://docs.github.com/en/get-started/getting-started-with-git/associating-text-editors-with-git



