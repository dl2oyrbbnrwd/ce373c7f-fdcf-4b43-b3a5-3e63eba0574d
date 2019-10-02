# Akvelon 2019 tasks

## requirements: msbuild 16.0

Create a Git repo locally or any remote one (github for example)

Add there 1 C++ and 2 C# projects where one of C# projects references another one

### Solution.sln
[Project_cpp](Project_cpp)    (C++)

[Project_cs_lib](Project_cs_lib)     (C# lib)

[Project_cs_app](Project_cs_app)  (C# console app, references [Project_cs_lib](Project_cs_lib))

## Automation

*Get code from Git repo to a local folder*

```
git clone https://github.com/dl2oyrbbnrwd/ce373c7f-fdcf-4b43-b3a5-3e63eba0574d.git
```

Modify project setting to enable debug symbols in release configuration of the projects

Build code in release configuration with any build engine/script (msbuild for example)

Calculate output files hashes for all binaries/assemblies and make hash/files manifest (xml or json for example)

Make a zip archive including all binaries/assemblies and generated manifest (use 7zip, Windows built in or any other)

Copy resulted zip to any release location

Copy resulted pdbs into a separate folder called Symbols in the same release location, saving original folder hierarchy.


## running tasks

"%path_to_msbuild%\MSBuild.exe" tasks.xml 

or (using custom release location folder)

"%path_to_msbuild%\MSBuild.exe" /p:ReleaseLocation=C:\Example tasks.xml 


### Please see [tasks.xml](tasks.xml) for inline comments
