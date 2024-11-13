# BlazzBass
A Starter Template for Blazor, Utilizing Bootstrap Saas

![GitHub Release](https://img.shields.io/github/v/release/twbs/Bootstrap?logo=bootstrap&logoColor=white&label=Bootstrap&link=https%3A%2F%2Fgithub.com%2Ftwbs%2Fbootstrap%2Freleases%2Flatest)


## Getting Started
This template utilize libman to manage and install bootstraps files, as of the last commit it is currently using bootstrap v5.3.3.  This is the *[documentation](https://learn.microsoft.com/en-us/aspnet/core/client-side/libman/libman-cli?view=aspnetcore-8.0)* for libman.

Clone this repo to your local device

### Setting up libman

#### Install libman

Launch your terminal and use the .net cli to install libman as a global tool

```
dotnet tool install -g Microsoft.Web.LibraryManager.Cli
```

#### Initialize libman

In your terminal navigate to the BlazzBaas Server Project.  There should already be a *'libman.json'* file with the following information in that file

```json
{
  "version": "1.0",
  "defaultProvider": "jsdelivr",
  "libraries": []
}
```

If this is not populated, or you can't locate it then you will need to initialize libman before bootstrap can be installed.  In the root of the repo enter the following command.

```
libman init -p jsdelivr
```

#### Installing bootstrap

Now that libman is initialized we can install bootstrap.  
