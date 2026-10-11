cmake_minimum_required(VERSION 3.16)
project(PhotosynthesisSim LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Tùy chọn: Dùng vcpkg để quản lý Raylib
# Nếu dùng vcpkg, bật dòng sau và chỉnh đường dẫn vcpkg của bạn
# set(CMAKE_TOOLCHAIN_FILE "C:/vcpkg/scripts/buildsystems/vcpkg.cmake")

# Tìm Raylib
find_package(raylib REQUIRED)

add_executable(PhotosynthesisSim main.cpp)
target_link_libraries(PhotosynthesisSim PRIVATE raylib)

# Nếu trên Windows và dùng Visual Studio, set startup project
if(MSVC)
    set_property(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR} PROPERTY VS_STARTUP_PROJECT PhotosynthesisSim)
endif()
