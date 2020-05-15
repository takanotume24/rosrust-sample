cmake_minimum_required(VERSION 3.0)
project(rust_pub)

find_package(catkin REQUIRED)
catkin_package()

add_custom_target(${PACKAGE_NAME}
    ALL
    COMMAND cargo build --release -p ${PACKAGE_NAME}
    COMMAND mkdir -p ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
    COMMAND cp $(HOME)/catkin_ws/build/cargo/release/${PACKAGE_NAME} ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/${PACKAGE_NAME}
    COMMENT "Building my Rust library"
)

