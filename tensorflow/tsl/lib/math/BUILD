load("//tensorflow:tensorflow.bzl", "get_compatible_with_portable")
load("//tensorflow:tensorflow.bzl", "tf_cc_test")

package(
    default_visibility = [
        "//tensorflow:__subpackages__",
    ],
    licenses = ["notice"],
)

cc_library(
    name = "math_util",
    hdrs = ["math_util.h"],
    compatible_with = get_compatible_with_portable(),
    deps = [
        "//tensorflow/tsl/platform:logging",
        "//tensorflow/tsl/platform:types",
    ],
)

tf_cc_test(
    name = "math_util_test",
    size = "small",
    srcs = [
        "math_util_test.cc",
    ],
    deps = [
        ":math_util",
        "//tensorflow/tsl/platform:logging",
        "//tensorflow/tsl/platform:test",
        "//tensorflow/tsl/platform:test_benchmark",
        "//tensorflow/tsl/platform:test_main",
        "//tensorflow/tsl/platform:types",
    ],
)

# Export source files needed for mobile builds, which do not use granular targets.
filegroup(
    name = "mobile_srcs_only_runtime",
    srcs = [
        "math_util.h",
    ],
    compatible_with = get_compatible_with_portable(),
    visibility = ["//tensorflow/core:__pkg__"],
)

exports_files([
    "math_util.h",
])
