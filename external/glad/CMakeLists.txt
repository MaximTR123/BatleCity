cmake_minimum_required(VERSION 3.13 FATAL_ERROR)

project(Glad)

add_library(glad STATIC includes/glad/glad.h srt/glad.c)
target_include_directories(glad PUBLIC include/)