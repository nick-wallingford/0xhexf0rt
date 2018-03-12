cmake_minimum_required(VERSION 3.10)
project(0xhexf0rt VERSION 0.0.1 LANGUAGES CXX)
add_executable(0xhexf0rt src/main.cpp)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_program(iwyu_path NAMES include-what-you-use iwyu)
if(iwyu_path)
  set_property(TARGET 0xhexf0rt
    PROPERTY CXX_INCLUDE_WHAT_YOU_USE
    ${iwyu_path})
endif()

target_compile_features(0xhexf0rt
  PRIVATE
  cxx_std_17
  )
target_compile_options(0xhexf0rt
  PRIVATE
  -Wall -Wextra
  )
