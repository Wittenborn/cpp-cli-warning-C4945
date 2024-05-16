cmake_minimum_required(VERSION 3.29)

project(C4945 VERSION 1.0.0 LANGUAGES CXX)


set(CMAKE_DOTNET_TARGET_FRAMEWORK "net8.0" CACHE STRING ".NET target framework")
string(REPLACE "/RTC1" "" CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG}")


add_library(C4945 SHARED C4945.cpp)

set_target_properties(C4945 PROPERTIES
    VS_GLOBAL_CLRSupport "NetCore"
    VS_USER_PROPS "${CMAKE_CURRENT_SOURCE_DIR}/C4945.props"
)

target_compile_options(C4945 PRIVATE "/EHa")
