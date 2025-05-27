cmake_minimum_required(VERSION 3.10)
project(solver_project VERSION 1.0.1)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(formatter_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(solver_lib)
add_subdirectory(solver_application)

install(TARGETS solver RUNTIME DESTINATION bin)


include(InstallRequiredSystemLibraries)
set(CPACK_DEBIAN_PACKAGE_MAINTAINER "iuwyr <egor.nalivajko@yandex.ru>")
set(CPACK_PACKAGE_NAME    "solver")
set(CPACK_PACKAGE_VERSION ${PROJECT_VERSION})

if(APPLE)
  set(CPACK_GENERATOR "TGZ;ZIP;DragNDrop")
elseif(WIN32)
  set(CPACK_GENERATOR "TGZ;ZIP;NSIS")
elseif(UNIX)
  set(CPACK_GENERATOR "TGZ;ZIP;DEB;RPM")
endif()

include(CPack)
