cmake_minimum_required(VERSION 2.9.0)
project(minunit_example)

file(GLOB SOURCE_FILES ${CMAKE_CURRENT_LIST_DIR}/*.cpp)

# Windows will do this automatically
if(${CMAKE_SYSTEM_NAME} MATCHES "Windows")
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/Output)
else()
  set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/Output/${CMAKE_BUILD_TYPE})
endif()

add_executable(minunit_example
    ${SOURCE_FILES}
    )