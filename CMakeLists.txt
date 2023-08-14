cmake_minimum_required(VERSION 3.5)
project(cLDtk C)


set(PROJECT_VERSION 1.0)
include (GNUInstallDirs)

add_library(cLDtk src/cLDtk.c src/parson.c)
target_include_directories(cLDtk PUBLIC $<INSTALL_INTERFACE:include>)

set_target_properties(cLDtk PROPERTIES PUBLIC_HEADER "cLDtk.h")
set_target_properties(cLDtk PROPERTIES VERSION ${PROJECT_VERSION})
set_target_properties(cLDtk PROPERTIES SOVERSION ${PROJECT_VERSION})