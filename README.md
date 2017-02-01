![](https://raw.githubusercontent.com/ecosystemsoftware/ecosystem-website/master/themes/ecosystem/static/images/eco-logo-colour.png)

# EcoSystem Custom Server Starter

This is a very simple starter file for creating a custom build of the [EcoSystem server](https://github.com/ecosystemsoftware/ecosystem-server) should you wish to add your own application-level functionality whilst still taking advantage of what the server already does.  Please check the main server repository for fuller instructions and documentation.

## Getting Started

These instructions are for building a *custom version of the EcoSystem server*.  You don't need to follow this if you just want to build and run the standard server.

### Instructions

The [EcoSystem server repository](https://github.com/ecosystemsoftware/ecosystem-server) is structured so that it can also be pulled in as a Go dependency for a simple custom build.  Make a project folder in your Go 'src' directory for your custom server and copy over the 'main.go' file from this repository.  Finally, fetch the server code using 'go get':

```
$ go get github.com/ecosystem-sofware/ecosystem-server
```

All the useful functionality in the EcoSystem server package lives in the 'utilities' subdirectory, so this is included as a package in 'main.go' like this:

```
eco "github.com/ecosystemsoftware/ecosystem-server/utilities"
```

If you copied over the 'main.go' file directly, this include is already done for you.

Now just go about building your server, using functionality from the EcoSystem server 'utilities' package.


### Licence

**Build freely with EcoSystem**.  The EcoSystem Server and The EcoSystem Admin Panel App are licensed under the [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0).  The content on the [EcoSystem website] (http://www.ecosystem.software) is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](http://creativecommons.org/licenses/by-nc-nd/4.0/).  Neither licence grants permission to use the trade names, trademarks, service marks, or product names of EcoSystem Software LLP, including the EcoSystem logo and symbol, except as required for reasonable and customary use.