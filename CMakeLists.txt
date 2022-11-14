cmake_minimum_required(VERSION 3.9)
project(asteroids)

set(CMAKE_CXX_STANDARD 11)

set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake")



find_package(SDL2 REQUIRED)
find_package(SDL2_ttf REQUIRED)
find_package(SDL2_image REQUIRED)


include_directories(${PROJECT_SOURCE_DIR}/source
        ${PROJECT_SOURCE_DIR}/source/SDL_draw
        ${SDL2_INCLUDE_DIR}
        ${SDL2_TTF_INCLUDE_DIR}
        ${SDL2_IMAGE_INCLUDE_DIR}
        )


file(GLOB SOURCE_FILES "source/*.cpp" source/SDL_draw/*.c source/SDL_draw/SDL_draw.h)


add_executable(cwing ${SOURCE_FILES})



target_link_libraries(cwing
        ${SDL2_LIBRARY}
        ${SDL2_TTF_LIBRARY}
        ${SDL2_IMAGE_LIBRARY}
        )

