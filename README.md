This is simply a minimal example to reproduce an issue I'm experiencing involving CMake configurations and C# in Visual Studio 2017 or 2019.

To reproduce, simply run CMake to configure & generate this project for Visual Studio. Then try building it. For me the output in Visual Studio 2017 was:

```
1>------ Build started: Project: ZERO_CHECK, Configuration: Debug Win32 ------
1>Checking Build System
2>------ Build started: Project: MultiConfigCSharpExample, Configuration: Debug Win32 ------
2>D:\CMakeCSharpRepro\Release\test.cs(3,11,3,15): error CS0101: The namespace 'Test' already contains a definition for 'Test'
2>D:\CMakeCSharpRepro\MinSizeRel\test.cs(3,11,3,15): error CS0101: The namespace 'Test' already contains a definition for 'Test'
2>D:\CMakeCSharpRepro\RelWithDebInfo\test.cs(3,11,3,15): error CS0101: The namespace 'Test' already contains a definition for 'Test'
2>D:\CMakeCSharpRepro\Release\test.cs(5,20,5,24): error CS0111: Type 'Test' already defines a member called 'Main' with the same parameter types
2>D:\CMakeCSharpRepro\MinSizeRel\test.cs(5,20,5,24): error CS0111: Type 'Test' already defines a member called 'Main' with the same parameter types
2>D:\CMakeCSharpRepro\RelWithDebInfo\test.cs(5,20,5,24): error CS0111: Type 'Test' already defines a member called 'Main' with the same parameter types
========== Build: 1 succeeded, 1 failed, 0 up-to-date, 0 skipped ==========
```
