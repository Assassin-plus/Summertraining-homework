cmake_minimum_required(VERSION 3.5)

project(protobuf_homework)

find_package(Protobuf REQUIRED)

message("${PROJECT_SOURCE_DIR}")

set(PROTOBUF_LIBPROTOBUF protobuf::libprotobuf)
message("Protobuf_INCLUDE_DIRS:${Protobuf_INCLUDE_DIRS}")
set(SOURCES src/player.pb.cc src/main.cpp)

# TODO 4:include the head files and use .cpp to generate executable
# add_executable
add_executable(protobuf_homework ${SOURCES})
# target_include_directories
target_include_directories(protobuf_homework PUBLIC ${PROJECT_SOURCE_DIR}/include)

target_link_libraries(protobuf_homework ${PROTOBUF_LIBPROTOBUF})