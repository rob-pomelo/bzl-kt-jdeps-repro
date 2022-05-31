load("@io_bazel_rules_kotlin//kotlin:jvm.bzl", "kt_jvm_binary", "kt_jvm_library", "kt_jvm_test")

kt_jvm_library(
    name = "runner_lib",
    srcs = ["Runner.kt"],
)

# Fails to build (`bazel build`).
kt_jvm_binary(
    name = "runner_failure",
    main_class = "examples.RunnerKt",
    runtime_deps = [":runner_lib"],
)

# Success
kt_jvm_binary(
    name = "runner_success",
    main_class = "examples.RunnerKt",
    srcs = ["Runner.kt"],
)

kt_jvm_library(
    name = "test_lib",
    srcs = ["TestExample.kt"],
    deps = [
        "@maven//:junit_junit",
    ],
)

# Fails to build (`bazel build`).
kt_jvm_test(
    name = "test_failure",
    test_class = "examples.TestExample",
    runtime_deps = [":test_lib"],
)

# Success to build (`bazel build`).
kt_jvm_test(
    name = "test_success",
    test_class = "examples.TestExample",
    srcs = ["TestExample.kt"],
    deps = [
        "@maven//:junit_junit",
    ],
)