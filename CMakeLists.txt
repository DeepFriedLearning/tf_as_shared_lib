cmake_minimum_required(VERSION 3.7)
project(tf_as_shared_lib)

set(CMAKE_CXX_STANDARD 11)

set(SOURCE_FILES main.cpp)

# set the path to the Tensorflow source root directory
set(TENSORFLOW_SOURCE_DIR /home/hal9000/Sources/tensorflow)

# where header files are found
INCLUDE_DIRECTORIES(
        ${TENSORFLOW_SOURCE_DIR}
        ${TENSORFLOW_SOURCE_DIR}/bazel-genfiles
        /usr/include/eigen3
)

# where libtensorflow resides (that we created by running `bazel build -c opt //tensorflow:libtensorflow.so`)
# see https://stackoverflow.com/questions/38256180/how-to-make-shared-libraries-with-bazel-at-tensorflow
LINK_DIRECTORIES(${TENSORFLOW_SOURCE_DIR}/bazel-bin/tensorflow)

add_executable(tf_as_shared_lib ${SOURCE_FILES})