# SPDX-License-Identifier: Apache-2.0
# SPDX-FileCopyrightText: 2019-2024 Second State INC

workspace(name = "wasmedge")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# Bazel rules for C/C++
http_archive(
    name = "rules_cc",
    sha256 = "2037875b9a4456dce4a79d112a8ae885bbc4aad968e6587dca6e64f3a0900cdf",
    strip_prefix = "rules_cc-0.0.9",
    urls = ["https://github.com/bazelbuild/rules_cc/releases/download/0.0.9/rules_cc-0.0.9.tar.gz"],
)

load("@rules_cc//cc:repositories.bzl", "rules_cc_dependencies")
rules_cc_dependencies()

# LLVM for AOT compilation
http_archive(
    name = "llvm-raw",
    build_file_content = "# empty",
    sha256 = "8daf2587b227f9dced08d51773e5a52a2e8945e57e0388d8d3d0b69f8e8c1be4",
    strip_prefix = "llvm-project-llvmorg-18.1.8",
    urls = ["https://github.com/llvm/llvm-project/archive/refs/tags/llvmorg-18.1.8.tar.gz"],
)

# LLVM Bazel overlay
http_archive(
    name = "llvm-bazel",
    sha256 = "62e4dd46c7d0ed557a7a8de6af1f4b834004d948cd3953bb1cdc8d8abe3bf0b6",
    strip_prefix = "llvm-bazel-main",
    urls = ["https://github.com/google/llvm-bazel/archive/refs/heads/main.zip"],
)

load("@llvm-bazel//:configure.bzl", "llvm_configure")
llvm_configure(name = "llvm-project")
