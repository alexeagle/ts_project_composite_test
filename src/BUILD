load("@npm_bazel_typescript//:index.bzl", "ts_project")

package(default_visibility = ["//:__subpackages__"])

ts_project(
    name = "tsconfig.esm",
    srcs = [],
    extends = ["//:tsconfig.json"],
    deps = ["@npm//:node_modules"],
)