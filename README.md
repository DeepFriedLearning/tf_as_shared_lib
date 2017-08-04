# tf_as_shared_lib

Trying to properly link Tensorflow to a C++ project with Cmake.

First, create libtensorflow.so by following the instructions here
https://stackoverflow.com/questions/38256180/how-to-make-shared-libraries-with-bazel-at-tensorflow

Then set the path to your Tensorflow source directory here https://github.com/DeepFriedLearning/tf_as_shared_lib/blob/master/CMakeLists.txt#L9
