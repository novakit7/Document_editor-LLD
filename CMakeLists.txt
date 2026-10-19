
cmake_minimum_required(VERSION 3.20)

project(DocsReader
    VERSION 1.0
    LANGUAGES CXX
)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(docs_reader
    src/main.cpp
    src/Client.cpp
    src/DBStorage.cpp
    src/Document.cpp
    src/DocumentEditor.cpp
    src/DocumentRenderer.cpp
    src/FileStorage.cpp
    src/ImageElement.cpp
    src/TextElement.cpp
)

target_include_directories(docs_reader
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/include
)

if(MSVC)
    target_compile_options(docs_reader PRIVATE /W4)
else()
    target_compile_options(docs_reader PRIVATE -Wall -Wextra -Wpedantic)
endif()
