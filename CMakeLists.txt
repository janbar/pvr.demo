project(pvr.demo)

cmake_minimum_required(VERSION 2.6)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${PROJECT_SOURCE_DIR})

enable_language(CXX)

find_package(kodi REQUIRED)
find_package(kodiplatform REQUIRED)
find_package(p8-platform REQUIRED)

include_directories(${kodiplatform_INCLUDE_DIRS}
                    ${p8-platform_INCLUDE_DIRS}
                    ${KODI_INCLUDE_DIR})

set(DEPLIBS ${kodiplatform_LIBRARIES}
            ${p8-platform_LIBRARIES})

set(PVRDEMO_SOURCES src/client.cpp
                    src/PVRDemoData.cpp)

build_addon(pvr.demo PVRDEMO DEPLIBS)

include(CPack)
