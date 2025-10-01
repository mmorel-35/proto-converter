workspace(name = "proto_converter")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# ============================================================================
# Dependencies synchronized between MODULE.bazel (bzlmod) and WORKSPACE modes
# ============================================================================
#
# Dependency Versions:
# - protobuf:       v29.3 (MODULE.bazel: 29.3, WORKSPACE: b407e8416e3893036aee5af9a12bd9b6a0e2b2e6)
# - googletest:     v1.15.0 (2024-07-15)
# - abseil-cpp:     Provided by protobuf_deps() - commit 4a2c63365eff8823a5221db86ef490e828306f9d (LTS 20240116.0)
# - bazel_skylib:   Provided by protobuf_deps() - 1.7.0
# - rules_cc:       Provided by protobuf_deps() - 0.0.16
# - rules_pkg:      Provided by protobuf_deps() - 1.0.1
# - rules_proto:    Not provided in WORKSPACE mode (MODULE.bazel: 6.0.2)
# - rules_python:   Provided by protobuf_deps() - 0.28.0
# - platforms:      Provided by protobuf_deps() - 0.0.7 (MODULE.bazel: 0.0.9)
#
# Note: Most dependencies are automatically provided by protobuf_deps() in WORKSPACE mode
# ============================================================================

# Protobuf v29.3 - synchronized with MODULE.bazel version 29.3
http_archive(
    name = "com_google_protobuf",
    sha256 = "55912546338433f465a552e9ef09930c63b9eb697053937416890cff83a8622d",
    strip_prefix = "protobuf-b407e8416e3893036aee5af9a12bd9b6a0e2b2e6",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/b407e8416e3893036aee5af9a12bd9b6a0e2b2e6.tar.gz"],  # v29.3
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

load("@rules_python//python/pip_install:repositories.bzl", "pip_install_dependencies")

pip_install_dependencies()

# GoogleTest v1.15.0 - synchronized with protobuf v29.3
http_archive(
    name = "com_google_googletest",
    sha256 = "7315acb6bf10e99f332c8a43f00d5fbb1ee6ca48c52f6b936991b216c586aaad",
    strip_prefix = "googletest-1.15.0",
    urls = [
        "https://github.com/google/googletest/releases/download/v1.15.0/googletest-1.15.0.tar.gz",  # 2024-07-15
    ],
)

load("@com_google_googletest//:googletest_deps.bzl", "googletest_deps")

googletest_deps()

