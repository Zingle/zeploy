The Zingle Deploy Protocol is used to provide hooks into project lifecycle
operations.  All protocol hooks are implemented as `make` targets.  Each hook
must be specified as a `.PHONY` target.

Protocol
========

Initialization
--------------
Create a `Makefile` in the project root and add a `.PHONY:` directive.

Hooks
-----
Each project hook must be specified as a `.PHONY` target.  No hooks are required
to be present.

### Hook: target-install
Execute installation of software on target system.  This happens before the
software is moved into place.

### Hook: target-reload
Reload any target system resources after an installation or upgrade of the
software.

Examples
========

Symfony
-------
```
APP = foo-app
PHPVER = 7.2

target-install:
    composer install
    phpunit

target-reload:
    cp /etc/zingle/$(APP).conf .env.local
    sudo systemctl restart php$(PHPVER)-fpm

.PHONY: install upgrade
```
