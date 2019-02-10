project(thread-utils)
cmake_minimum_required(VERSION 3.1)

set(CMAKE_CXX_STANDARD 14)
#add_subdirectory(fmt)
include_directories(${CMAKE_SOURCE_DIR})
include_directories(/opt/local/include)
link_directories(/opt/local/lib)

add_executable(test_worker examples/test_worker.cc)
target_link_libraries(test_worker fmt pthread)

add_executable(test_queue examples/test_queue.cc)
target_link_libraries(test_queue fmt pthread)

add_executable(test_main test/test_main.cc test/test_queue.cc)
