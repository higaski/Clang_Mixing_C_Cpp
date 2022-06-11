Fails to build on Clang
```sh
/usr/bin/clang++   -std=gnu++2b -MD -MT CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o -MF CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o.d -o CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o -c /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/main.cpp
In file included from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/main.cpp:1:
In file included from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/cpp_header.hpp:3:
In file included from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/c_header.h:7:
/home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/config.h:13:23: error: redefinition of 'v'
inline constexpr auto v = 41;
                      ^
/home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/config.h:7:23: note: previous definition is here
inline constexpr auto v = 42;
                      ^
1 error generated.
ninja: build stopped: subcommand failed.
```

But builds with GCC (although with warning)
```sh
[1/2] /usr/bin/c++   -std=gnu++23 -MD -MT CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o -MF CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o.d -o CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o -c /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/main.cpp
In file included from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/c_header.h:7,
                 from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/cpp_header.hpp:3,
                 from /home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/main.cpp:1:
/home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/config.h:13:23: warning: conflicting C language linkage declaration ‘constexpr const auto b::v’
   13 | inline constexpr auto v = 41;
      |                       ^
/home/vinci/Develop/VSCode/Clang_Mixing_C_Cpp/src/config.h:7:23: note: previous declaration ‘constexpr const int a::v’
    7 | inline constexpr auto v = 42;
      |                       ^
[2/2] : && /usr/bin/c++   CMakeFiles/Clang_Mixing_C_Cpp.dir/src/main.cpp.o -o Clang_Mixing_C_Cpp   && :
```