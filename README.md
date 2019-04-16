The Zingle zeploy tool is used to deploy Zingle applications to the server
infrastructure.

Installation
============

```sh
sudo -H npm install -g @zingle/zeploy
```

Basic Usage
===========

```sh
cd my-project
zeploy server01.zingle.me:/usr/local/my-app
```

Using Without NPM
=================

```sh
cd my-project
wget -qO- https://raw.githubusercontent.com/Zingle/zeploy/master/bin/zeploy \
    | bash -s -- server01.zingle.me:/usr/local/my-app
```

More information
================
For more information, see the [documentation](doc/overview.md).
