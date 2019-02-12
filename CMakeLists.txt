cmake_minimum_required(VERSION 3.9)
project(CoreApp)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

set(SOURCE_FILES
  App.cpp
  pch.cpp
  )

set(HEADER_FILES
  pch.h
  )

set(ASSET_FILES
    Assets/Logo.scale-100.png
    Assets/SmallLogo.scale-100.png
    Assets/SplashScreen.scale-100.png
    Assets/StoreLogo.scale-100.png
    Assets/WideLogo.scale-100.png
    )

set(CONTENT_FILES
    Package.appxmanifest
    )

set(RESOURCE_FILES
  ${CONTENT_FILES} ${ASSET_FILES}
  CoreApp_TemporaryKey.pfx)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

set_property(SOURCE ${CONTENT_FILES} PROPERTY VS_DEPLOYMENT_CONTENT 1)
set_property(SOURCE ${ASSET_FILES} PROPERTY VS_DEPLOYMENT_CONTENT 1)
set_property(SOURCE ${ASSET_FILES} PROPERTY VS_DEPLOYMENT_LOCATION "Assets")

source_group("Source Files" FILES ${SOURCE_FILES})
source_group("Header Files" FILES ${HEADER_FILES})
source_group("Resource Files" FILES ${RESOURCE_FILES})

add_executable(CoreApp WIN32 ${SOURCE_FILES} ${HEADER_FILES} ${RESOURCE_FILES})

set_target_properties(CoreApp PROPERTIES COMPILE_FLAGS "/Yupch.h")
set_source_files_properties(pch.cpp PROPERTIES COMPILE_FLAGS "/Ycpch.h")

set_target_properties(CoreApp PROPERTIES
  CXX_STANDARD 17
)

SET(CPPWINRT_REQUIRED_COMPILER_FLAGS "/std:c++latest /await")
SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} ${CPPWINRT_REQUIRED_COMPILER_FLAGS}")
