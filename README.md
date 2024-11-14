# BlazzBaas

A Starter Template for Blazor, Utilizing Bootstrap Saas with LibMan

[![GitHub Release](https://img.shields.io/github/v/release/twbs/Bootstrap?logo=bootstrap&logoColor=white&label=Bootstrap)](https://github.com/twbs/bootstrap/releases/latest)

This template uses LibMan (Library Manager) to manage and install Bootstrap files, The badge above displays the latest Bootstrap release version, currently set to Bootstrap v5.3.3. For additional details, refer to the official *[LibMan documentation](https://learn.microsoft.com/en-us/aspnet/core/client-side/libman/libman-cli?view=aspnetcore-8.0)*.

## 📦 Dependencies

Before you begin, ensure the following dependencies are installed. Documentation links are included for help with installation:

- [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
- [.Net 8 SDK](https://learn.microsoft.com/en-us/dotnet/core/install/)
- [LibMan Cli](https://learn.microsoft.com/en-us/aspnet/core/client-side/libman/libman-cli?view=aspnetcore-8.0#installation)

## 💻 Installation

### Clone the Repository

#### 1. Clone the Repository

Start by cloning the BlazzBass repository from GitHub:

```git
git clone https://github.com/your-username/BlazzBass.git
```

#### 2. Navigate to the Server Project Directory

Change to the Blazor server project directory:

```shell
cd BlazzBass
```

### Automated Setup with LibMan Build Target

#### 1. Add LibMan Build Package

To configure automatic fetching of dependencies during the build, install the LibMan build package:

```shell
dotnet add package Microsoft.Web.LibraryManager.Build --version 2.1.175
```

#### 2. Configure Bootstrap in libman.json

Ensure libman.json in the project directory includes the following configuration to specify Bootstrap v5.3.3 (or replace 5.3.3 with the latest version shown in the badge above if a newer version is available):

```json
{
  "version": "1.0",
  "defaultProvider": "jsdelivr",
  "libraries": [
    {
      "library": "bootstrap@5.3.3",
      "destination": "wwwroot/lib/bootstrap"
    }
  ]
}
```

#### 3. Build the project

Run the following command to build the project, which will also install Bootstrap and any other dependencies listed in libman.json:

```shell
dotnet build
```

#### 4. Verify app.scss Configuration

Confirm that the following content is in the app.scss file located in wwwroot:

```scss
// 1. Include functions first to enable color, SVG, and calculation utilities
@import "../lib/bootstrap/scss/functions";

// 2. Override any default variables as needed
$primary: hsl(265, 65%, 35%);

// 3. Import the rest of Bootstrap
@import "../lib/bootstrap/scss/bootstrap";

// 4. Add any additional custom code here

// Original app.css
```

There should already be a *'libman.json'* file with the following information in that file

```json
{
  "version": "1.0",
  "defaultProvider": "jsdelivr",
  "libraries": []
}
```

If this is not populated, or you can't locate it then you will need to initialize libman before bootstrap can be installed.  

In the server project directory, run the following command in your shell:

```shell
libman init -p jsdelivr
```

### Installing bootstrap

Now that libman is initialized we can install bootstrap.

In the server project directory, run the following command in your shell.

```shell
libman install bootstrap@5.3.3 -d lib/bootstrap
```

### Verify app.scss Contents

Ensure your app.scss file is configured correctly to use Bootstrap and any custom styles. Follow the steps below to confirm the contents of your app.scss file, located in the wwwroot directory of your server project:

1. Navigate to the wwwroot Directory
Open the app.scss file in the wwwroot directory of your server project.
2. Verify the Content of app.scss
Confirm that the following code is included in your app.scss file, in the specified order:

```scss
// 1. Include functions first to enable color, SVG, and calculation utilities
@import "../lib/bootstrap/scss/functions";

// 2. Override any default variables as needed
$primary: hsl(265, 65%, 35%);

// 3. Import the rest of Bootstrap
@import "../lib/bootstrap/scss/bootstrap";

// 4. Add any additional custom code here

// Original app.css
```

#### Explanation of Steps

**Step 1:** imports Bootstrap’s utility functions.  
**Step 2:** defines the primary color.  
**Step 3:** imports the main Bootstrap styles.  
**Step 4:** is for any additional custom code.  

After completing these steps, Bootstrap will be installed and ready for use in your project without needing any manual steps.

<!-- TODO Add steps for compiling scss to css and creating css.min files -->

<!-- TODO Add instructions for updating bootstrap version -->