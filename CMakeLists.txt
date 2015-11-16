
cmake_minimum_required(VERSION 2.8.9)
if(COMMAND CMAKE_POLICY)
  cmake_policy(SET CMP0003 NEW)
endif()

include_directories(${LIBRABBITMQ_INCLUDE_DIRS})
set(COMMON_SRCS
    utils.h
    utils.c
    )


# This project is designed to be built outside the Insight source tree.
project(test)

# Find ITK.
# find_package(/home/zshen/src/rabbitmq-client/rabbitmq-c/librabbitmq/cmake)
# include(/home/zshen/src/rabbitmq-client/rabbitmq-c/)

add_executable(test test.cpp send.cpp send.h ${COMMON_SRCS})
message(STATUS ${RMQ_LIBRARY_TARGET})
# target_link_libraries(test "/home/zshen/src/rabbitmq-client/rabbitmq-c/librabbitmq/librabbitmq.so")
target_link_libraries(test "rabbitmq")


