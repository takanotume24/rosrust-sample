cmake_minimum_required(VERSION 3.0)
project(rust_pub)

find_package(catkin REQUIRED)
catkin_package()


add_custom_target(rust_pub
    ALL
    COMMAND cargo build --release -p rust_pub
    COMMAND mkdir -p ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
    COMMAND cp $(HOME)/catkin_ws/build/cargo/release/rust_pub ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/rust_pub
    COMMENT "Building my Rust library"
)

