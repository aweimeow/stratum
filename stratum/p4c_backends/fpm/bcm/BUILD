#
# Copyright 2018 Google LLC
# Copyright 2018-present Open Networking Foundation
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#

licenses(["notice"])  # Apache v2

load(
    "//bazel:rules.bzl",
    "STRATUM_INTERNAL",
)

package(
    # default_copts = [
    #     "-DDISABLE_GOOGLE_GLOBAL_USING_DECLARATIONS",
    # ],
    # default_hdrs_check = "warn",
    default_visibility = STRATUM_INTERNAL,
)

cc_library(
    name = "bcm_target_info",
    srcs = [
        "bcm_target_info.cc",
    ],
    hdrs = [
        "bcm_target_info.h",
    ],
    copts = [
        "-fexceptions",
    ],
    features = ["-use_header_modules"],  # Incompatible with -fexceptions.
    deps = [
        "//stratum/p4c_backends/fpm:target_info",
        "//stratum/public/proto:p4_annotation_cc_proto",
    ],
)

cc_test(
    name = "bcm_target_info_test",
    srcs = [
        "bcm_target_info_test.cc",
    ],
    copts = [
        "-fexceptions",
    ],
    data = [
        "//stratum/p4c_backends/fpm:testdata/pipeline_opt_block.ir.json",
    ],
    features = ["-use_header_modules"],  # Incompatible with -fexceptions.
    deps = [
        ":bcm_target_info",
        "@com_google_googletest//:gtest_main",
        "//stratum/public/proto:p4_annotation_cc_proto",
    ],
)

cc_library(
    name = "bcm_tunnel_optimizer",
    srcs = [
        "bcm_tunnel_optimizer.cc",
    ],
    hdrs = [
        "bcm_tunnel_optimizer.h",
    ],
    copts = [
        "-fexceptions",
    ],
    features = ["-use_header_modules"],  # Incompatible with -fexceptions.
    deps = [
        "@com_github_google_glog//:glog",
        "@com_google_protobuf//:protobuf",
        "//stratum/p4c_backends/fpm:p4c_switch_utils",
        "//stratum/p4c_backends/fpm:tunnel_optimizer_interface",
        "//stratum/hal/lib/p4:p4_table_map_cc_proto",
        "//stratum/public/proto:p4_table_defs_cc_proto",
    ],
)

cc_test(
    name = "bcm_tunnel_optimizer_test",
    srcs = [
        "bcm_tunnel_optimizer_test.cc",
    ],
    copts = [
        "-fexceptions",
    ],
    features = ["-use_header_modules"],  # Incompatible with -fexceptions.
    linkopts = [
        "-lgmp",
        "-lgmpxx",
    ],
    deps = [
        ":bcm_tunnel_optimizer",
        "@com_google_googletest//:gtest_main",
        "@com_github_p4lang_p4c//:p4c_toolkit",
        "//stratum/hal/lib/p4:p4_table_map_cc_proto",
        "//stratum/lib:utils",
        "//stratum/public/proto:p4_table_defs_cc_proto",
    ],
)
