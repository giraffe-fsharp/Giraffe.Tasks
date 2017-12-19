# Giraffe.Tasks

![Giraffe](https://raw.githubusercontent.com/giraffe-fsharp/Giraffe/master/giraffe.png)

A task computation expression which works natively with .NET's Task objects from an F# application.

[![NuGet Info](https://buildstats.info/nuget/Giraffe.Tasks?includePreReleases=true)](https://www.nuget.org/packages/Giraffe.Tasks/)

| Windows | Linux |
| :------ | :---- |
| [![Windows Build status](https://ci.appveyor.com/api/projects/status/914030ec0lrc0vti/branch/develop?svg=true)](https://ci.appveyor.com/project/dustinmoris/giraffe-tasks/branch/develop) | [![Linux Build status](https://travis-ci.org/giraffe-fsharp/Giraffe.Tasks.svg?branch=develop)](https://travis-ci.org/giraffe-fsharp/Giraffe.Tasks/builds?branch=develop) |
| [![Windows Build history](https://buildstats.info/appveyor/chart/dustinmoris/giraffe-tasks?branch=develop&includeBuildsFromPullRequest=false)](https://ci.appveyor.com/project/dustinmoris/giraffe-tasks/history?branch=develop) | [![Linux Build history](https://buildstats.info/travisci/chart/giraffe-fsharp/Giraffe.Tasks?branch=develop&includeBuildsFromPullRequest=false)](https://travis-ci.org/giraffe-fsharp/Giraffe.Tasks/builds?branch=develop) |

## Table of contents

- [Documentation](#documentation)
- [Nightly builds and NuGet feed](#nightly-builds-and-nuget-feed)
- [More information](#more-information)
- [License](#license)

## Documentation

The `Giraffe.Tasks` NuGet package adds native support for .NET's `Task` and `Task<'T>` objects to an F# application. By using the `Giraffe.Tasks` module an ASP.NET Core/Giraffe web application can benefit of significant performance boosts by removing the necessity of manually converting between .NET's tasks and F#'s async workflows.

After opening the `Giraffe` or `Giraffe.Tasks` module you can use the `task {}` computation expression to work natively with .NET's tasks objects. It works syntactically almost identical to F#'s `async {}` workflow.

The original code has been taken from [Robert Peele](https://github.com/rspeele)'s [TaskBuilder.fs](https://github.com/rspeele/TaskBuilder.fs) and gradually modified to better fit Giraffe's use case for highly scalable ASP.NET Core web applications.

### Example:

```fsharp
open System.IO
open Giraffe.Tasks

// This function will return an object of type Task<string> instead of Async<string>
let readFileAndDoSomething (filePath : string) =
    task {
        use stream = new FileStream(filePath, FileMode.Open)
        use reader = new StreamReader(stream)
        let! contents = reader.ReadToEndAsync()

        // do something with contents

        return contents
    }
```

The `task {}` computation expression also allows you to await an `Async<'T>` workflow without having to convert it into a `Task<'T>` beforehand.

## Nightly builds and NuGet feed

All official Giraffe packages are published to the official and public NuGet feed.

Unofficial builds (such as pre-release builds from the `develop` branch and pull requests) produce unofficial pre-release NuGet packages which can be pulled from the project's public NuGet feed on AppVeyor:

```
https://ci.appveyor.com/nuget/giraffe-tasks
```

If you add this source to your NuGet CLI or project settings then you can pull unofficial NuGet packages for quick feature testing or urgent hot fixes.

## More information

For more information about Giraffe, how to set up a development environment, contribution guidelines and more please visit the [main documentation](https://github.com/giraffe-fsharp/Giraffe#table-of-contents) page.

## License

[Apache 2.0](https://raw.githubusercontent.com/giraffe-fsharp/Giraffe.Tasks/master/LICENSE)