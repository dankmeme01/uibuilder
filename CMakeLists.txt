cmake_minimum_required(VERSION 3.21.0)
project(UIBuilder VERSION 1.0.0 LANGUAGES CXX)

add_library(${PROJECT_NAME} INTERFACE)

target_include_directories(${PROJECT_NAME} INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})
target_compile_features(${PROJECT_NAME} INTERFACE cxx_std_20)


CPMAddPackage("gh:zhihaoy/nontype_functional#bdb0987")
target_link_libraries(${PROJECT_NAME} INTERFACE nontype_functional)
target_compile_definitions(${PROJECT_NAME} INTERFACE UIBUILDER_USE_CUSTOM_FUNCTION=1)
