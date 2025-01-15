cmake_minimum_required(VERSION 3.30)
project(SpaceInvaders)

set(CMAKE_CXX_STANDARD 20)
# Find OpenGL
find_package(OpenGL REQUIRED)

# Find GLFW
find_package(glfw3 3.3 REQUIRED)

# Add GLAD source files (assuming they are in a "src" subdirectory)
add_executable(SpaceInvaders1
        src/main.cpp
        src/glad.c
        src/game.cpp
        src/entity.cpp
        # ... other source files for your project
)

# Include directories
target_include_directories(SpaceInvaders1 PUBLIC
        ${OPENGL_INCLUDE_DIRS}
        ${glfw3_INCLUDE_DIRS}
        ${CMAKE_CURRENT_SOURCE_DIR}/include # Include directory for GLAD headers
        # ... other include directories
)

# Link libraries
target_link_libraries(SpaceInvaders1 PUBLIC
        ${OPENGL_LIBRARIES}
        ${glfw3_LIBRARIES}
        # ... other libraries
)
add_executable(SpaceInvaders src/main.cpp)
