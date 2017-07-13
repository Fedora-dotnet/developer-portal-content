---
title: C# - .Net Usage
subsection: csharp
order: 3
---


# DotNet Usage

**General Usage**:  
`dotnet [host-options] [command] [arguments] [common-options]`

**Arguments:** 

|      Arguments     |            Description            |
| :----------------: | :-------------------------------: |
|    `[command]`     |      The Command to Execute       |
|   `[arguments]`    | Arguments to pass to the command  |
|  `[host-options]`  | Options specific to dotnet (host) |
| `[common-options]` |  Options common to all commands   |

**Common options:**  

|       Option       |            Description            |
| :----------------: | :-------------------------------: |
|   `-v/--verbose`   |       Enable verbose output       |
|    `-h/--help`     |             Show help             |


**Host options (passed before the command):**  

|        Option        |           Description           |
| :------------------: | :-----------------------------: |
| `-d / --diagnostics` |    Enable diagnostic output     |
|     `--version`      | Display .NET CLI Version Number |
|       `--info`       |      Display .NET CLI Info      |


**Commands:**  

|  Command  |               Description                |
| :-------: | :--------------------------------------: |
|   `new`   |         Initialize .NET projects         |
| `restore` | Restore dependencies specified in the .NET project |
|  `build`  |          Builds a .NET project           |
| `publish` | Publishes a .NET project for deployment (including the runtime) |
|   `run`   | Compiles and immediately executes a .NET project |
|  `test`   | Runs unit tests using the test runner specified in the project |
|  `pack`   |         Creates a NuGet package          |
| `migrate` | Migrates a project.json based project to a msbuild based project |
|  `clean`  |          Clean build output(s)           |
|   `sln`   |       Modify solution (SLN) files        |


**Project modification commands:**  

|  Command |          Description          |
| :------: | :---------------------------: |
|  `add`   |   Add items to the project    |
| `remove` | Remove items from the project |
|  `list`  |   List items in the project   |


**Advanced Commands:** 

|  Syntax   |               Description                |
| :-------: | :--------------------------------------: |
|  `nuget`  |    Provides additional NuGet commands    |
| `msbuild` |  Runs Microsoft Build Engine (MSBuild)   |
| `vstest`  | Runs Microsoft Test Execution Command Line Tool |

---



# Template Instantiation Commands for .NET Core CLI

**Usage:**  
`dotnet new [arguments][options]`  

**Arguments:**  
`template`			The template to instantiate.  

**Options:**  

|       Option       |               Description                |
| :----------------: | :--------------------------------------: |
|    `-l / --list`     | List templates containing the specified name |
| `-lang / --language` | Specifies the language of the template to create |
|    `-n / --name`     | The name for the output being created. If no name is specified, the name of the current directory is used |
|   `-o / --output`    |  Location to place the generated output  |
|    `-h / --help`     |      Displays help for this command      |
| `-all / --show-all`  |           Shows all templates            |


---



# .NET Dependency Restorer

**Usage:**  
`dotnet restore [arguments] [options] [args]`  

**Arguments:**
`[Project]`							Optional path to a project file or MSBuild arguments.  

**Options:**

|                  Option                  |               Description                |
| :--------------------------------------: | :--------------------------------------: |
|                `-h / --help`                |          Show help information           |
|       `-s / --source <SOURCE>`        | Specifies a NuGet package source to use during the restore |
| `-r / --runtime <RUNTIME_IDENTIFIER>` |  Target runtime to restore packages for  |
|  `--packages <PACKAGES_DIRECTORY>`   |     Directory to install packages in     |
|            `--disable-parallel`            | Disables restoring multiple projects in parallel |
|        `--configfile <FILE>`         |   The NuGet configuration file to use    |
|                `--no-cache`                | Do not cache packages and http requests  |
|         `--ignore-failed-sources`          | Treat package source failures as warnings |
|            `--no-dependencies`             | Set this flag to ignore project to project references and only restore the root project |
|             `-v / --verbosity`              | Set the verbosity level of the command. Allowed values are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic] |


---



# .NET Builder

**Usage:**  
`dotnet build [arguments] [options] [args]`  

**Arguments:**  
`<PROJECT>`							The MSBuild project file to build.  

**Options:**  

|                  Option                  |               Description                |
| :--------------------------------------: | :--------------------------------------: |
|                `-h / --help`                |          Show help information           |
|     `-o / --output <OUTPUT_DIR>`      | Specifies a NuGet package source to use during the restore |
|    `-f / --framework <FRAMEWORK>`     |  Target runtime to restore packages for  |
| `-r / --runtime <RUNTIME_IDENTIFIER>` |     Directory to install packages in     |
| `-c / --configuration <CONFIGURATION>` | Disables restoring multiple projects in parallel |
| `--version-suffix <VERSION_SUFFIX>`  |   The NuGet configuration file to use    |
|             `--no-incremental`             | Do not cache packages and http requests  |
|            `--no-dependencies`             | Set this flag to ignore project to project references and only restore the root project |
|             `-v / --verbosity`              | Set the verbosity level of the command. Allowed values are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic] |

---



# .Net Publisher

**Usage:**  
`dotnet publish [arguments] [options] [args]`  

**Arguments:**  
`<PROJECT>`							The MSBuild project file to publish.  

**Options:**  

|                  Option                  |               Description                |
| :--------------------------------------: | :--------------------------------------: |
|                `-h / --help`                |          Show help information           |
|    `-f / --framework <FRAMEWORK>`     | Target framework to build for. The target framework has to be in the project file |
| `-r / --runtime <RUNTIME_IDENTIFIER>` | Target runtime to build for. The default is to build a portable	application |
|     `-o / --output <OUTPUT_DIR>`      | Output directory in which to place built artifacts |
| `-c / --configuration <CONFIGURATION>` | Configuration to use for building the project. Default for most projects is  "Debug" |
| `--version-suffix <VERSION_SUFFIX>`  | Defines the value for the $(VersionSuffix) property in the project |
|             `-v / --verbosity`              | Set the verbosity level of the command. Allowed values are q[uiet], m[inimal], n[ormal], d[etailed], and diag[nostic] |
