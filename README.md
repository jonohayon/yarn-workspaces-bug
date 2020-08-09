Yarn workspaces bug
===

This repo showcases the bug found in yarnpkg/yarn#5476, where post/preinstall scripts won't output to stdout (and are not being run in certain circumstances).

In order to reproduce the bug, run `yarn` from the root of the project. The post/preinstall scripts of `package-a` won't show up in the stdout stream, but the
failing scripts in `package-b` and `package-c` will (one of them in random, since yarn is doing parallel work). This was made in order to make sure that the scripts
are actually being run and to make sure the problem is the output to stdout.
