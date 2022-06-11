cmake_minimum_required(VERSION 3.19)

project(Mixing_C_Cpp LANGUAGES C CXX)

file(GLOB_RECURSE SRC src/*.cpp)
add_executable(Mixing_C_Cpp ${SRC})

target_compile_features(Mixing_C_Cpp PUBLIC cxx_std_23)
