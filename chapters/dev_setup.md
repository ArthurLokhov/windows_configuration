# Development setup

## .Net
1. Download [`.Net SDK`](https://dotnet.microsoft.com/en-us/download) and install it.
2. Check if you install correct or not:
```ps1
dotnet --list-sdks
dotnet --list-runtimes
dotnet new --list
dotnet nuget list source
dotnet nuget add source https://api.nuget.org/v3/index.json -n nuget.org # If previous line has empty output.
```
3. Download [`Visual Studio 2022 Build Tools`](https://aka.ms/vs/17/release/vs_BuildTools.exe) and install it.

## Install other software
1. Download `Windows Terminal` from `MS Store`.

## VSCode
1. `Extensions`:
- C#.
- C# Xml Documentation Comments.
- C# Snippets.
- Path Intellisense.
- .NET Core Test Explorer.
- Nuget Gallery.
- Error Lens.
- Toml.

2. `Settings`:
```json
// DotNet development
"omnisharp.enableEditorConfigSupport": true,
"omnisharp.enableRoslynAnalyzers": true,
// DotNet development
```

3. `omnisharp.conf`:
```conf
{
    "RoslynExtensionsOptions": {
        "enableAnalyzersSupport": true
    },
    "FormattingOptions": {
        "enableEditorConfigSupport": true,
        "OrganizeImports": true
    },
    "RenameOptions": {
        "RenameInComments": true,
        "RenameOverloads": true,
        "RenameInStrings": true
    },
    "ImplementTypeOptions": {
        "PropertyGenerationBehavior": "PreferAutoProperties|PreferThrowingProperties",
        "InsertionBehavior": "AtTheEnd|WithOtherMembersOfTheSameKind"
    }
}
```

## Next...
Chapter 4: [`Shell configuration`](./shell_configuration.md).