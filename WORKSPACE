workspace(
    name = "test",
    managed_directories = {"@npm": ["node_modules"]},
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "d0c4bb8b902c1658f42eb5563809c70a06e46015d64057d25560b0eb4bdc9007",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/1.5.0/rules_nodejs-1.5.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

node_repositories(
    package_json = ["//:package.json"],
    node_version = "13.9.0",
    node_repositories = {
        "13.9.0-darwin_amd64": ("node-v13.9.0-darwin-x64.tar.gz", "node-v13.9.0-darwin-x64", "b2a5a539b9b2d1733bda301913c99d220968de801bf313b762fa932820ea797b"),
        "13.9.0-linux_amd64": ("node-v13.9.0-linux-x64.tar.xz", "node-v13.9.0-linux-x64", "f1e093303468032a1ecb0e290e19b43bf7771d4efbf589560df0060149614272"),
        "13.9.0-windows_amd64": ("node-v13.9.0-win-x64.zip", "node-v13.9.0-win-x64", "ec0a55bb703906494e738cd3d09e3274b34f0a3fbe207b9e67502092ed017500"),
    },
    node_urls = ["https://nodejs.org/dist/v{version}/{filename}"],
    yarn_repositories = {
        "1.21.1": ("yarn-v1.21.1.tar.gz", "yarn-v1.21.1", "d1d9f4a0f16f5ed484e814afeb98f39b82d4728c6c8beaafb5abc99c02db6674"),
    },
    yarn_urls = ["https://github.com/yarnpkg/yarn/releases/download/v{version}/{filename}"],
    yarn_version = "1.21.1",
)

yarn_install(
    # Name this npm so that Bazel Label references look like @npm//package
    name = "npm",
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

load("@npm//:install_bazel_dependencies.bzl", "install_bazel_dependencies")

install_bazel_dependencies()

