load("@npm_bazel_typescript//:index.bzl", "ts_project")

package(default_visibility = ["//:__subpackages__"])

ts_project(
    name = "tsconfig.bzl",
    composite = True,
    declaration = True,
    declaration_map = True,
    extends = [
        "//:tsconfig.json",
        "//src:tsconfig.esm.json",
        ":tsconfig.json",
    ],
    incremental = True,
    source_map = True,
    deps = []
)

