cmake_minimum_required( VERSION 3.19 )
project( MultiConfigCSharpExample LANGUAGES CSharp )
add_executable( ${PROJECT_NAME} "${CMAKE_SOURCE_DIR}/$<CONFIG>/test.cs" )
target_compile_options( ${PROJECT_NAME} PRIVATE "/langversion:6" )
set_target_properties( ${PROJECT_NAME} PROPERTIES
  FOLDER SomeFolder
  DOTNET_TARGET_FRAMEWORK_VERSION "v4.6.1"
  VS_DOTNET_REFERENCES "Microsoft.CSharp;System;System.Runtime;System.Runtime.InteropServices"
)
