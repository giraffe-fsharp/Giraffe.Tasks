# Giraffe.Tasks (Deprecated)

![Giraffe](https://raw.githubusercontent.com/giraffe-fsharp/Giraffe/master/giraffe.png)

A task computation expression which works natively with .NET's Task objects from an F# application.


## Attention: This NuGet package has been deprecated!

The [Giraffe.Tasks NuGet package](https://www.nuget.org/packages/Giraffe.Tasks/) has been deprecated in favour of migrating Giraffe to the original [TaskBuilder.fs](https://www.nuget.org/packages/TaskBuilder.fs/) NuGet library.

Please note that `Giraffe.Tasks` was a copy of [TaskBuilder.fs](https://github.com/rspeele/TaskBuilder.fs) from the beginning of its time and replacing `Giraffe.Tasks` with [TaskBuilder.fs](https://github.com/rspeele/TaskBuilder.fs) in your project should be as straight forward as a simple change in your dependencies definition and opening a new namespace:

```fsharp
open FSharp.Control.Tasks.ContextInsensitive
```

This change has been introduced with the [release of Giraffe 1.0.0](https://dusted.codes/announcing-giraffe-100).

This project is not being maintained any longer. If you have any issues with tasks in F# then please open an issue in the [TaskBuilder.fs repository](https://github.com/rspeele/TaskBuilder.fs).

## More information

For more information about Giraffe, how to set up a development environment, contribution guidelines and more please visit the [main documentation](https://github.com/giraffe-fsharp/Giraffe/blob/master/DOCUMENTATION.md) page.

## License

[Apache 2.0](https://raw.githubusercontent.com/giraffe-fsharp/Giraffe.Tasks/master/LICENSE)