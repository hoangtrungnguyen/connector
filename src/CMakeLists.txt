# The Flutter tooling requires that developers have CMake 3.10 or later
# installed. You should not increase this version, as doing so will cause
# the plugin to fail to compile for some customers of the plugin.
cmake_minimum_required(VERSION 3.10)

project(connector_library VERSION 0.0.1 LANGUAGES C)

add_library(connector SHARED
  "connector.c"
)

set_target_properties(connector PROPERTIES
  PUBLIC_HEADER connector.h
  OUTPUT_NAME "connector"
)

target_compile_definitions(connector PUBLIC DART_SHARED_LIB)
