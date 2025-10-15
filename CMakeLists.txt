cmake_minimum_required(VERSION 4.0.4 FATAL_ERROR)

set(PROJECT_NAME BatleCity)
project(${PROJECT_NAME})

# Создаем исполнимый файл
add_executable(${PROJECT_NAME} src/main.cpp)

# Отключаем ненужные опции для GLFW
set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
set(GLFW_INSTALL OFF CACHE BOOL "" FORCE)

# Добавляем подкаталоги для внешних зависимостей
add_subdirectory(external/glfw)
add_subdirectory(external/glad)

# Линкуем библиотеки
target_link_libraries(${PROJECT_NAME} PRIVATE glfw glad)
