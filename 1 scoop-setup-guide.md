# Java Angular/Enterprise Setup Guide

This guide will take you through the process of setting up your environment to be ready for the Java/Angular Enterprise training. It will make sure you have everything that you need downloaded and set up!

## Scoop

Scoop is a package manager for Windows. It makes it super easy to download everything and manage the versions as needed. You can install it by following the directions [here](https://scoop.sh/), which I'll repeat below. If you are not using Windows, you can try Homebrew for macOS or an appropriate package manager for your Linux distribution. However, this guide will assume that you are running Scoop, so you'll need to figure anything else out on your own.

1. Open up PowerShell.
2. Run the following command:
```
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser # Optional: Needed to run a remote script the first time
> irm get.scoop.sh | iex
```
3. Now that you have Scoop, you may need to close and re-open your PowerShell before you can run Scoop commands.
4. Scoop provides "buckets" of different software that you can install. There are a few buckets you'll need. Run this command to add them:
```
scoop bucket add extras
scoop bucket add java
scoop bucket add versions
```
5. You should be good to go! Now that you have Scoop and the necessary buckets, installing the other software you need will be quick and easy.

## Git

Git is our source code management tool/version control manager. **This is necessary from the very first day of training.** You can install Git for Windows with Scoop, but installing it via [the website](https://gitforwindows.org/) is actually easier because it gives you some extra options with Git BASH (the bash terminal that we can use with Git commands), so that's what I recommend.

## Java

We will be using Java 8 during training. If you already have a newer version installed, that is fine, but make sure that you have a **JDK**, not just a JRE. Run this Scoop command to install JDK 8.
``` sh
scoop install ojdkbuild8
```
To make sure that you installed Java, try running these commands:
``` sh
java --version
javac -version
```
If these don't work, you may need to set up your environment variables. [This link](https://www.codejava.net/java-core/how-to-set-environment-variables-for-java-using-command-line) will help you with that, and it tells you how to do it both using the Windows GUI and the command line so you can choose what you prefer. The location of Java will be in your `~/scoop` folder, so you'll want to look for the correct path there.

## Maven

Maven is a build automation tool that will make it significantly easier to create Java applications with external libraries/frameworks. Install it with the following command.
```
scoop install maven
```

## Eclipse IDE

We use Eclipse IDE for Java in training; specifically, you will probably want Eclipse for Java EE Developers (which is different from standard Eclipse). You may have used IntelliJ before, and if you prefer it, you're welcome to continue using it, but know that I will not always be able to help you with some setup, so you should feel comfortable using it or looking up how to do things like create a Maven project or run JUnit tests. If you want to keep it simple, install Eclipse with the following command:
```
scoop install eclipse-jee
```

## Visual Studio Code

VS Code is a powerful text editor that can be used for basically any type of file that we'll be working with in training. It makes it easy to do things like fix merge conflicts in Git, run commands on a file you're working with, or just navigate an Angular project, and it has tons of extensions that you can use to customize it to your liking. Run the following command to install it:
```
scoop install vscode
```

## AWS

AWS is the cloud platform that we'll use in this training. All that you need to do is make an account. **You should do this in advance because sometimes it can take a few days to verify your account.** By "in advance", I mean before the second week of training. Everything that we'll be doing in training will fall under AWS's free tier. Make an account [here](https://aws.amazon.com).

## DBeaver

DBeaver is a client for accessing databases. It makes it easy to interact with your SQL database without having to use the command line - it has a nice interface with lots of helpful tools. Install it with the following command.
```
scoop install dbeaver
```

## PostgreSQL

PostgreSQL is a relational database management system or RDBMS. It's basically a specific type of server for SQL, like mySQL or Oracle SQL. PostgreSQL is the RDBMS that we use in training. This installation is actually not required, because you can use AWS to run your PostgreSQL server, but a local one will be faster so if you are able to do it, it will make it a little bit easier when testing your projects.
1. Install PostgreSQL.
```
scoop install postgresql
```
2. When you are ready to run your local PostgreSQL database, start it with the following command.
```
pg_ctl start
```
3. The default username is typically `postgres` and the default password is empty. Sometimes the default username will be set to your computer username so if `postgres` doesn't work, try that.
4. If you need to stop your local database (maybe at the end of training or after you are selected by a client), run the following.
```
pg_ctl stop
```

## Postman

Postman is an API testing tool. It makes it easy to send all sorts of HTTP requests to your API, save requests or groups of requests, and even set up actual test scripts. We will start using it at the end of week 3. Also, if you prefer, you can use Insomnia instead.
```
scoop install postman
```

## Node.js

Node is a server-side JavaScript environment. We won't be writing server-side JavaScript, but Node provides us with two things: a way to run Angular apps locally, and most importantly, NPM, Node Package Manager, which is what allows us to install Angular and manage Angular's dependencies to begin with. Because Angular requires specific versions of Node, we are not going to install Node directly, but rather we are going to use NVM, Node Version Manager. Use the following commands.
```
scoop install nvm
# you may need to restart your PowerShell before you can run the next command
nvm install 16
```
I recommend that you have this installed by week 6 as we will start using it at the end of that week.