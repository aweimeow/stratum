#
# Copyright 2018-present Barefoot Networks, Inc.
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
    "stratum_cc_library",
    "stratum_cc_test",
    "HOST_ARCHES",
)

package(
    default_visibility = STRATUM_INTERNAL,
)

pi_node_common_deps = [
    "@com_google_googleapis//google/rpc:status_cc_proto",
    "@com_github_p4lang_p4runtime//:p4info_cc_proto",
    "@com_github_p4lang_p4runtime//:p4runtime_cc_grpc",
    "//stratum/glue:integral_types",
    "//stratum/glue:logging",
    "//stratum/glue/status:status_macros",
    "//stratum/hal/lib/common:writer_interface",
    "//stratum/lib:constants",
    "//stratum/lib:macros",
    "//stratum/hal/lib/common:common_cc_proto",
]

# Default PI Node
stratum_cc_library(
    name = "pi_node",
    srcs = ["pi_node.cc"],
    hdrs = ["pi_node.h"],
    deps = pi_node_common_deps +
           ["@com_github_p4lang_PI//proto/frontend:pifeproto"]
)

# PI Node for Barefoot targets
stratum_cc_library(
    name = "pi_node_bf",
    srcs = ["pi_node.cc"],
    hdrs = ["pi_node.h"],
    deps = pi_node_common_deps +
           ["@com_github_p4lang_PI_bf//proto/frontend:pifeproto"]
)