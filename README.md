# PHP IntelliSense

> **⚠ Work In Progress**

[![Latest Release](https://vsmarketplacebadge.apphb.com/version-short/felixfbecker.php-intellisense.svg)](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-intellisense) [![Installs](https://vsmarketplacebadge.apphb.com/installs/felixfbecker.php-intellisense.svg)](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-intellisense) [![Rating](https://vsmarketplacebadge.apphb.com/rating-short/felixfbecker.php-intellisense.svg)](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-intellisense) [![Build Status](https://travis-ci.org/felixfbecker/vscode-php-intellisense.svg?branch=master)](https://travis-ci.org/felixfbecker/vscode-php-intellisense) [![Dependency Status](https://gemnasium.com/felixfbecker/vscode-php-intellisense.svg)](https://gemnasium.com/felixfbecker/vscode-php-intellisense) [![Gitter](https://badges.gitter.im/felixfbecker/vscode-php-intellisense.svg)](https://gitter.im/felixfbecker/vscode-php-intellisense?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

Advanced PHP IntelliSense for Visual Studio Code.
In opposite to the included PHP IntelliSense and other PHP extensions, this uses an AST to parse the source code
instead of relying on naive regular expression parsing.

## Features

### Find all symbols
![Find all symbols demo](images/documentSymbol.gif)

### Column-accurate error reporting
![Error reporting demo](images/publishDiagnostics.png)


## Todo
 - Autocompletion
 - Rename
 - Goto definition
 - Format document
 - Hover
 - Signature help
 - Follow composer autoloading


## Contributing

This is just the VS Code extension that spawns the actual language server. The language server itself is implemented purely in PHP [in its own repository](https://github.com/felixfbecker/php-language-server), all features need to be implemented there and all issues should be reported there.

### Build and Run From Source
Clone whole repository and in root directory execute:
```bash
composer install 
npm install
npm run compile
code .
```
The last command will open the folder in VS Code. Hit `F5` to launch an Extension Development Host with the extension.
For working on the language server, the easiest way is to replace the language server installation from composer in `vendor/felixfbecker/language-server` with a symlink to your local clone.

## Debug
XDebug needs to be configured for remote debugging. Check if *ini* file contains necessary parameters:
```
xdebug.remote_enable = 1
xdebug.remote_autostart = 1
xdebug.remote_connect_back = 1
xdebug.remote_port = 9000
xdebug.remote_handler=dbgp
xdebug.remote_host=localhost
```
### Configure VS Code
TODO

### Configure PDT
Download Eclipse package with PHP support ([PHP EPP](http://www.eclipse.org/downloads/packages/eclipse-php-developers/neonr))

* Start PDT
* Import extension project with File -> Open Project from File System
* Set breakpoint in PHP language server source code
