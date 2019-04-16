The Zingle Deploy Protocol is used to provide hooks into project lifecycle
operations.  All protocol hooks are implemented as `make` targets.  Each hook
must be specified as a `.PHONY` target.

Protocol
========

Before You Begin
----------------
Create a `Makefile` in the project root and add a `.PHONY:` directive.  This
file will contain all the custom steps necessary to properly build and deploy
your project.

Hooks
-----
Each project hook must be specified as a `.PHONY` target.  Simply adding a
target is not enough.  No hooks are required to be present.

### Hook: target-install
Execute installation of software on target system.  This happens after the
software has been copied to the target, but before the software is moved into
its final destination.

### Hook: target-reload
Reload any target system resources after an installation or upgrade of the
software.

Examples
--------

 * [Symfony](example/Makefile.symfony)
