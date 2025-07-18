# Copyright 2025 gRPC authors.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

load("//bazel:grpc_build_system.bzl", "grpc_cc_library", "grpc_cc_test")

# This library generates experiment header and source files for RPC frameworks.
# To ensure its usability for other RPC frameworks, avoid adding any gRPC-specific dependencies.
grpc_cc_library(
    name = "experiments_compiler",
    srcs = ["experiments_compiler.cc"],
    hdrs = ["experiments_compiler.h"],
    external_deps = [
        "absl/log",
        "absl/log:check",
        "absl/status",
        "absl/status:statusor",
        "absl/strings",
        "absl/strings:str_format",
        "absl/time:time",
        "absl/container:flat_hash_map",
        "yaml-cpp",
    ],
    visibility = ["//visibility:public"],
)

grpc_cc_test(
    name = "experiments_compiler_test",
    srcs = ["experiments_compiler_test.cc"],
    external_deps = [
        "gtest",
        "absl/log:log",
        "absl/status",
        "absl/container:flat_hash_map",
    ],
    deps = [
        ":experiments_compiler",
        "//test/core/test_util:grpc_test_util",
        "//test/cpp/util:test_config",
    ],
)
