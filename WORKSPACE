http_archive(
    name = "io_bazel_rules_closure",
    sha256 = "6691c58a2cd30a86776dd9bb34898b041e37136f2dc7e24cadaeaf599c95c657",
    strip_prefix = "rules_closure-08039ba8ca59f64248bb3b6ae016460fe9c9914f",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_closure/archive/08039ba8ca59f64248bb3b6ae016460fe9c9914f.tar.gz",
        "https://github.com/bazelbuild/rules_closure/archive/08039ba8ca59f64248bb3b6ae016460fe9c9914f.tar.gz",  # 2018-01-16
    ],
)

new_git_repository(
    name = "org_lame",
    build_file = "lame.BUILD",
    commit = "3f89eaa001d9cc5a52e88f6b493c6eec750e9eab",
    remote = "https://github.com/lifeiteng/lame.git",
)

new_git_repository(
    name = "org_opus",
    build_file = "opus.BUILD",
    tag = "v1.3-rc2",
    remote = "https://github.com/xiph/opus.git",
)
