# Dogma Dart Libraries

> Documentation Site for the Dogma libraries for Dart

[![Build Status](http://beta.drone.io/api/badges/dogma-dart/dogma-dart.github.io/status.svg)](http://beta.drone.io/dogma-dart/dogma-dart.github.io)

[![Join the chat at https://gitter.im/dogma-dart/dogma-dart.github.io](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/dogma-dart/dogma-dart.github.io?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

## Setup

All documentation development occurs on the
[develop](https://github.com/dogma-dart/dogma-dart.github.io/tree/develop) 
branch of the repository. Any modifications should be done on this branch as
the master branch is just the static site that was generated during the build.

### Hugo

This website uses the [Hugo](https://github.com/spf13/hugo) static site
generator. If you are planning to contribute you'll want to download and install
Hugo on your local machine.

Follow these instructions for your platform at 
http://gohugo.io/overview/installing/ to begin.

### Theme

This website uses the 
[Hugo Project Homepage](https://github.com/donny-dont/hugo-project-homepage)
theme. To install after the initial clone and checkout of the develop branch run
the following commands.

```
mkdir themes
cd themes
git clone https://github.com/donny-dont/hugo-project-homepage.git
```

## Build

To generate the website and output to `./public` run the following command.

```
hugo
```
