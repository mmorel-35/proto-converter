workspace(name = "proto_converter")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

# ============================================================================
# Dependencies synchronized between MODULE.bazel (bzlmod) and WORKSPACE modes
# ============================================================================
#
# Dependency Versions:
# - protobuf:       v26.0 (MODULE.bazel: 26.0.bcr.1, WORKSPACE: d6511091a0cab1ad13f676a02676ad2a0e5eb9ae)
# - googletest:     f53219cdcb7b084ef57414efea92ee5b71989558 (2023-03-16)
# - abseil-cpp:     Provided by protobuf_deps() - commit 4a2c63365eff8823a5221db86ef490e828306f9d (LTS 20240116.0)
# - bazel_skylib:   Provided by protobuf_deps() - 1.3.0
# - rules_cc:       Provided by protobuf_deps() - commit c8c38f8c710cbbf834283e4777916b68261b359c (0.0.9)
# - rules_pkg:      Provided by protobuf_deps() - 0.7.0
# - rules_proto:    Provided by protobuf_deps() - 5.3.0-21.7
# - rules_python:   Provided by protobuf_deps() - 0.26.0
# - platforms:      Provided by protobuf_deps() - 0.0.7 (MODULE.bazel: 0.0.9)
#
# Note: Most dependencies are automatically provided by protobuf_deps() in WORKSPACE mode
# ============================================================================

# Protobuf v26.0 - synchronized with MODULE.bazel version 26.0.bcr.1
http_archive(
    name = "com_google_protobuf",
    sha256 = "5d1ffa6bd21ee09dd0a87d6126ca5b3b608f131cf1c4a4a0ccd8c141b37069b9",
    strip_prefix = "protobuf-d6511091a0cab1ad13f676a02676ad2a0e5eb9ae",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/d6511091a0cab1ad13f676a02676ad2a0e5eb9ae.tar.gz"],  # v26.0
)

load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")

protobuf_deps()

load("@rules_python//python:repositories.bzl", "py_repositories")

py_repositories()

# GoogleTest - synchronized with protobuf v26.0
http_archive(
    name = "com_google_googletest",
    sha256 = "730215d76eace9dd49bf74ce044e8daa065d175f1ac891cc1d6bb184ef94e565",
    strip_prefix = "googletest-f53219cdcb7b084ef57414efea92ee5b71989558",
    urls = [
        "https://github.com/google/googletest/archive/f53219cdcb7b084ef57414efea92ee5b71989558.tar.gz",  # 2023-03-16
    ],
)

load("@com_google_googletest//:googletest_deps.bzl", "googletest_deps")

googletest_deps()

