---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Git"
subtitle: "Software for tracking changes."
summary: "Post about git"
authors: [Khoshkhoev. A. B.]
tags: []
categories: []
date: 2022-05-06T18:48:37+03:00
lastmod: 2022-05-06T18:48:37+03:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

![](https://fuzeservers.ru/wp-content/uploads/4/c/a/4ca54660353facf2dab077639fb18a8b.png)

## Overview

Git (/git/) is a software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different systems).

Git was originally authored by Linus Torvalds in 2005 for development of the Linux kernel, with other kernel developers contributing to its initial development. Since 2005, Junio Hamano has been the core maintainer. As with most other distributed version control systems, and unlike most client-server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking abilities, independent of network access or a central server. Git is free and open-source software distributed under the GPL-2.0-only license.

## History

Git development began in April 2005, after many developers of the Linux kernel gave up access to BitKeeper, a proprietary source-control management (SCM) system that they had been using to maintain the project since 2002. The copyright holder of BitKeeper, Larry McVoy, had withdrawn free use of the product after claiming that Andrew Tridgell had created SourcePuller by reverse engineering the BitKeeper protocols. The same incident also spurred the creation of another version-control system, Mercurial.

Linus Torvalds wanted a distributed system that he could use like BitKeeper, but none of the available free systems met his needs. Torvalds cited an example of a source-control management system needing 30 seconds to apply a patch and update all associated metadata, and noted that this would not scale to the needs of Linux kernel development, where synchronizing with fellow maintainers could require 250 such actions at once. For his design criterion, he specified that patching should take no more than three seconds, and added three more goals:

Take Concurrent Versions System (CVS) as an example of what not to do; if in doubt, make the exact opposite decision.
Support a distributed, BitKeeper-like workflow.
Include very strong safeguards against corruption, either accidental or malicious.
These criteria eliminated every version-control system in use at the time, so immediately after the 2.6.12-rc2 Linux kernel development release, Torvalds set out to write his own.

The development of Git began on 3 April 2005. Torvalds announced the project on 6 April and became self-hosting the next day. The first merge of multiple branches took place on 18 April. Torvalds achieved his performance goals; on 29 April, the nascent Git was benchmarked recording patches to the Linux kernel tree at the rate of 6.7 patches per second. On 16 June, Git managed the kernel 2.6.12 release.

Torvalds turned over maintenance on 26 July 2005 to Junio Hamano, a major contributor to the project. Hamano was responsible for the 1.0 release on 21 December 2005 and remains the project's core maintainer.

## Design

Git's design was inspired by BitKeeper and Monotone. Git was originally designed as a low-level version-control system engine, on top of which others could write front ends, such as Cogito or StGIT. The core Git project has since become a complete version-control system that is usable directly. While strongly influenced by BitKeeper, Torvalds deliberately avoided conventional approaches, leading to a unique design.

## Implementations

Git (the main implementation in C) is primarily developed on Linux, although it also supports most major operating systems, including the BSDs (DragonFly BSD, FreeBSD, NetBSD, and OpenBSD), Solaris, macOS, and Windows.

The first Windows port of Git was primarily a Linux-emulation framework that hosts the Linux version. Installing Git under Windows creates a similarly named Program Files directory containing the Mingw-w64 port of the GNU Compiler Collection, Perl 5, MSYS2 (itself a fork of Cygwin, a Unix-like emulation environment for Windows) and various other Windows ports or emulations of Linux utilities and libraries. Currently, native Windows builds of Git are distributed as 32- and 64-bit installers. The git official website currently maintains a build of Git for Windows, still using the MSYS2 environment.

The JGit implementation of Git is a pure Java software library, designed to be embedded in any Java application. JGit is used in the Gerrit code-review tool, and in EGit, a Git client for the Eclipse IDE.

Go-git is an open-source implementation of Git written in pure Go. It is currently used for backing projects as a SQL interface for Git code repositories and providing encryption for Git.

The Dulwich implementation of Git is a pure Python software component for Python 2.7, 3.4 and 3.5.

The libgit2 implementation of Git is an ANSI C software library with no other dependencies, which can be built on multiple platforms, including Windows, Linux, macOS, and BSD. It has bindings for many programming languages, including Ruby, Python, and Haskell.

JS-Git is a JavaScript implementation of a subset of Git.

## Security

Git does not provide access-control mechanisms, but was designed for operation with other tools that specialize in access control.

On 17 December 2014, an exploit was found affecting the Windows and macOS versions of the Git client. An attacker could perform arbitrary code execution on a target computer with Git installed by creating a malicious Git tree (directory) named .git (a directory in Git repositories that stores all the data of the repository) in a different case (such as .GIT or .Git, needed because Git does not allow the all-lowercase version of .git to be created manually) with malicious files in the .git/hooks subdirectory (a folder with executable files that Git runs) on a repository that the attacker made or on a repository that the attacker can modify. If a Windows or Mac user pulls (downloads) a version of the repository with the malicious directory, then switches to that directory, the .git directory will be overwritten (due to the case-insensitive trait of the Windows and Mac filesystems) and the malicious executable files in .git/hooks may be run, which results in the attacker's commands being executed. An attacker could also modify the .git/config configuration file, which allows the attacker to create malicious Git aliases (aliases for Git commands or external commands) or modify extant aliases to execute malicious commands when run. The vulnerability was patched in version 2.2.1 of Git, released on 17 December 2014, and announced the next day.

Git version 2.6.1, released on 29 September 2015, contained a patch for a security vulnerability (CVE-2015-7545) that allowed arbitrary code execution. The vulnerability was exploitable if an attacker could convince a victim to clone a specific URL, as the arbitrary commands were embedded in the URL itself. An attacker could use the exploit via a man-in-the-middle attack if the connection was unencrypted, as they could redirect the user to a URL of their choice. Recursive clones were also vulnerable, since they allowed the controller of a repository to specify arbitrary URLs via the gitmodules file.

Git uses SHA-1 hashes internally. Linus Torvalds has responded that the hash was mostly to guard against accidental corruption, and the security a cryptographically secure hash gives was just an accidental side effect, with the main security being signing elsewhere. Since a demonstration of the SHAttered attack against git in 2017, git was modified to use a SHA-1 variant resistant to this attack. A plan for hash function transition is being written since February 2020.