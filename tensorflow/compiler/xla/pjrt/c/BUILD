load("//tensorflow/tsl/platform:rules_cc.bzl", "cc_library")

# copybara:uncomment package(default_applicable_licenses = ["//tensorflow:license"])

cc_library(
    name = "pjrt_c_api_hdrs",
    hdrs = ["pjrt_c_api.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/compiler/xla/stream_executor/tpu:c_api_decl",  # TODO(b/238999986): Remove this.
    ],
)

cc_library(
    name = "pjrt_c_api_tpu_hdrs",
    hdrs = ["pjrt_c_api_tpu.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":pjrt_c_api_hdrs",
    ],
)

cc_library(
    name = "pjrt_c_api_wrapper_impl",
    srcs = ["pjrt_c_api_wrapper_impl.cc"],
    hdrs = ["pjrt_c_api_wrapper_impl.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":pjrt_c_api_hdrs",
        ":pjrt_c_api_helpers",
        "//tensorflow/compiler/xla:literal",
        "//tensorflow/compiler/xla:shape_util",
        "//tensorflow/compiler/xla:status",
        "//tensorflow/compiler/xla:statusor",
        "//tensorflow/compiler/xla/client:xla_computation",
        "//tensorflow/compiler/xla/pjrt:mlir_to_hlo",
        "//tensorflow/compiler/xla/pjrt:pjrt_client",
        "//tensorflow/compiler/xla/pjrt:pjrt_executable",
        "//tensorflow/compiler/xla/pjrt:pjrt_future",
        "//tensorflow/compiler/xla/service:hlo_proto_cc",
        "//tensorflow/compiler/xla/stream_executor/tpu:c_api_conversions",  # TODO(b/238999986): Remove this.
    ],
)

cc_library(
    name = "pjrt_c_api_helpers",
    srcs = ["pjrt_c_api_helpers.cc"],
    hdrs = ["pjrt_c_api_helpers.h"],
    visibility = ["//visibility:public"],
    deps = [
        ":pjrt_c_api_hdrs",
        "//tensorflow/compiler/xla:shape_util",
        "//tensorflow/compiler/xla:status",
        "//tensorflow/compiler/xla:xla_data_proto_cc",
        "//tensorflow/compiler/xla/pjrt:pjrt_client",
    ],
)
