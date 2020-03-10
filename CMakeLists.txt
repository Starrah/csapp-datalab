# Use this in your Makefile to enable debug
# ifeq ($(DEBUG), true)
# CFLAGS = (other flags) -g -DDEBUG 
# endif
# 
# gcc $(CFLAGS) xxx.c
# 
# Then run make in remote system with bash

cmake_minimum_required(VERSION 3.4.1)
project(datalab)
message(${datalab_SOURCE_DIR})
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_VERBOSE_MAKEFILE 1)
add_custom_target(run
        COMMAND make clean -C ${datalab_SOURCE_DIR}
        COMMAND make -C ${datalab_SOURCE_DIR}
        CLION_EXE_DIR=${PROJECT_BINARY_DIR}
        )
add_custom_target(runWithDebug
        COMMAND make clean -C ${datalab_SOURCE_DIR}
        COMMAND make -C ${datalab_SOURCE_DIR}
        DEBUG=true
        CLION_EXE_DIR=${PROJECT_BINARY_DIR}
        )