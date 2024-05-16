# cpp-cli-warning-C4945
Minimal example showing how warning C4945 is generated when compiling a C++/CLI project referencing the Microsoft.WindowsDesktop.App framework as described in the [documentation](https://learn.microsoft.com/en-us/dotnet/core/porting/cpp-cli#wpf-and-windows-forms-usage).

Run:

    cmake -G "Visual Studio 17 2022" -S . -B ..\build && cmake --build ..\build

There should be multiple [warnings C4945](https://learn.microsoft.com/en-us/cpp/error-messages/compiler-warnings/compiler-warning-level-1-c4945?view=msvc-170):

> warning C4945: 'BulletChrome': cannot import symbol from 'C:\Program Files\dotnet\packs\Microsoft.WindowsDesktop.App.Ref\8.0.5\ref\net8.0\PresentationFramework.Aero2.dll': as 'Microsoft::Windows::Themes::BulletChrome' has already been imported from another assembly 'C:\Program Files\dotnet\packs\Microsoft.WindowsDesktop.App.Ref\8.0.5\ref\net8.0\PresentationFramework.Aero.dll'

Tested on Windows 11 with:
Microsoft Visual Studio Professional 2022 (64-Bit) 17.9.5, Windows SDK version 10.0.22621.0, MSVC 19.39.33523.0, MSBuild 17.9.8+b34f75857, dotnet SDK 8.0.300, CMake 3.29.3
