# CMakeList.txt : CMake project for CMakeProject1, include source and define
# project specific logic here.
#

find_package(Matplot++ REQUIRED)
find_package(PythonLibs REQUIRED)
find_package(Python3 REQUIRED COMPONENTS Interpreter Development)
find_package(Python3 COMPONENTS Interpreter NumPy)


# Add source to this project's executable.
add_executable (CMakeProject1 "CMakeProject1.cpp" "CMakeProject1.h" "matplotlibcpp.h")
target_link_libraries(CMakeProject1 PUBLIC Python3::NumPy)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET CMakeProject1 PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
