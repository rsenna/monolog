cmake_minimum_required(VERSION 3.29)
project(monolog)
set(CMAKE_CXX_STANDARD 17)

find_package(PkgConfig REQUIRED)
include_directories(${PROJECT_SOURCE_DIR})

set(MACOS_HOMEBREW_CELLAR /opt/homebrew/Cellar)
message(MACOS_HOMEBREW_CELLAR="${MACOS_HOMEBREW_CELLAR}")

execute_process(COMMAND id)

execute_process(
        COMMAND bash -c "find ${MACOS_HOMEBREW_CELLAR}/allegro -type d -maxdepth 1 | tail -n 1 | tr -d '\n'"
        OUTPUT_VARIABLE MACOS_HOMEBREW_ALLEGRO )

message(MACOS_HOMEBREW_ALLEGRO="${MACOS_HOMEBREW_ALLEGRO}")

set(MACOS_ALLEGRO_INCLUDE "${MACOS_HOMEBREW_ALLEGRO}/include")
message(MACOS_ALLEGRO_INCLUDE="${MACOS_ALLEGRO_INCLUDE}")

set(MACOS_ALLEGRO_LIB "${MACOS_HOMEBREW_ALLEGRO}/lib" )
message(MACOS_ALLEGRO_LIB="${MACOS_ALLEGRO_LIB}")

include_directories( ${MACOS_ALLEGRO_INCLUDE} )
link_directories( ${MACOS_ALLEGRO_LIB} )

add_executable(monolog main.cpp)

pkg_check_modules(allegro-5 REQUIRED allegro-5)
target_link_libraries(monolog ${ALLEGRO5_LIBRARIES})
target_include_directories(monolog PUBLIC ${ALLEGRO5_INCLUDE_DIRS})

