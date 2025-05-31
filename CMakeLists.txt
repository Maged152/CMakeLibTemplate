cmake_minimum_required(VERSION 3.22)
project(CMakeLibTemplate VERSION 1.0.0 LANGUAGES CXX)

# used in tests and examples
set(PARENT_PROJECT_NAME ${PROJECT_NAME})

# Enable CTest and options only for the main project
if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    include(CTest)
    option(CMakeLibTemplate_BUILD_TESTING "Enable testing" ON)
    option(CMakeLibTemplate_BUILD_EXAMPLES "Enable examples" ON)
endif()

option(CMakeLibTemplate_BUILD_DOC "Build documentations" ON)

# Create the library
add_subdirectory(lib)

# Check if testing is enabled
if(CMakeLibTemplate_BUILD_TESTING AND BUILD_TESTING)
    message(STATUS "Testing for ${PROJECT_NAME} is enabled")
    add_subdirectory(tests)
endif()

# Check if examples are enabled
if(CMakeLibTemplate_BUILD_EXAMPLES)
    message(STATUS "Examples for ${PROJECT_NAME} are enabled")
    add_subdirectory(examples)
endif()

# Check if documentations are enabled
if(CMakeLibTemplate_BUILD_DOC)
    message(STATUS "documentations for ${PROJECT_NAME} are enabled")
    add_subdirectory(doc)
endif()
