cmake_minimum_required(VERSION 3.23)

project(cactuar
        VERSION 0.0.1
        DESCRIPTION ""
        LANGUAGES C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 20)

set(CMAKE_MODULE_PATH 
  "${PROJECT_SOURCE_DIR}/cmake"
  ${CMAKE_MODULE_PATH}
  )

include(LibUtils)

set_property(GLOBAL PROPERTY USE_FOLDERS ON)

if (MSVC)
  add_compile_options(/W4) # /WX)
else()
  add_compile_options(-Wall -Wextra -pedantic) # -Werror)
endif()

set(MODULE_ROOT "${PROJECT_SOURCE_DIR}/include")

add_subdirectory(cactuar)
add_subdirectory(bindings)
add_subdirectory(app)
