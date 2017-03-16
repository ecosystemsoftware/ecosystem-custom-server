![](https://raw.githubusercontent.com/ecosystemsoftware/ecosystem-website/master/themes/ecosystem/static/images/ecosystem-logo.png)

# EcoSystem Custom Server Starter

This is a very simple starter file for creating a custom build of the [EcoSystem server](https://github.com/ecosystemsoftware/ecosystem) should you wish to add your own application-level functionality whilst still taking advantage of what the server already does.  Please check the main server repository for fuller instructions and documentation.

## Getting Started

These instructions are for building a *custom version of the EcoSystem server*.  You don't need to follow this if you just want to build and run the standard server.

### Instructions

The [EcoSystem server repository](https://github.com/ecosystemsoftware/ecosystem) is structured so that it can also be pulled in as a Go dependency for a simple custom build.  Make a project folder in your Go 'src' directory for your custom server and copy over the 'main.go' file from this repository.  Finally, fetch the server code using 'go get':

```
$ go get github.com/ecosystemsofware/ecosystem-server
```

EcoSystem functionality is organised into standard Go packages, so these are included as imports in the `main.go`.  All you need to do is import additional packages and bootstrap them in your main.go.  Your whole main.go file will look like this:

```
package main

import (
	"github.com/ecosystemsoftware/ecosystem/auth"
	"github.com/ecosystemsoftware/ecosystem/core"
	"github.com/ecosystemsoftware/ecosystem/email"
)

func main() {

	//Tell EcoSystem which packages to activate
	core.ActivatePackages = activatePackages

	//Bootstrap the application
	core.RootCmd.Execute()
}

func activatePackages() {
	//Standard packages
	core.Activate()
	auth.Activate()
	email.Activate()

	//Bootstrap other packages here
    //e.g. images.Activate()

}

```

### Licence

**Build freely with EcoSystem**.  The EcoSystem Server and The EcoSystem Admin Panel App are licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).  The content on the [EcoSystem website] (http://www.ecosystem.software) is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](http://creativecommons.org/licenses/by-nc-nd/4.0/).  Neither licence grants permission to use the trade names, trademarks, service marks, or product names of EcoSystem Software, including the EcoSystem logo and symbol, except as required for reasonable and customary use.