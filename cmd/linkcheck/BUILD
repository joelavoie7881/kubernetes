package(default_visibility = ["//visibility:public"])

load(
    "//build:go.bzl",
    go_binary = "go_binary_conditional_pure",
)
load("@io_bazel_rules_go//go:def.bzl", "go_library")

go_binary(
    name = "linkcheck",
    embed = [":go_default_library"],
)

go_library(
    name = "go_default_library",
    srcs = ["links.go"],
    importpath = "k8s.io/kubernetes/cmd/linkcheck",
    deps = [
        "//vendor/github.com/mvdan/xurls:go_default_library",
        "//vendor/github.com/spf13/pflag:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)
