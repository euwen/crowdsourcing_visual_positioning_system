cmake_minimum_required(VERSION 3.1)
project(backend)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

add_definitions(--std=c++11 -Wno-unknown-pragmas -DVISUALIZATION)

cs_add_library(${PROJECT_NAME}_lib
    src/find_correspond.cc
    src/pose_graph_opti.cc
    src/ba.cc
    src/culling_frame.cc
    src/map_tool.cc
    src/cal_subgroup.cc
)

cs_add_executable(${PROJECT_NAME}
    src/main.cc
)
target_link_libraries(${PROJECT_NAME} ${PROJECT_NAME}_lib)

cs_install()
cs_export()
