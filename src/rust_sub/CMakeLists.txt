cmake_minimum_required(VERSION 3.0)
project(rust_sub)

find_package(catkin REQUIRED)
catkin_package()

add_custom_target(rust_sub
    ALL
    COMMAND cargo build --release -p rust_sub
    COMMAND mkdir -p ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}
    COMMAND cp /root/catkin_ws/build/cargo/release/rust_sub ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/rust_sub
    COMMENT "Building my Rust library"
)

