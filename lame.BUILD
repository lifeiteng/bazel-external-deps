licenses(["notice"])

genrule(
    name = "config_h",
    srcs = [
        "configure",
        "libmp3lame/lame.c",
        "install-sh",
        "config.guess",
        "config.rpath",
        "config.sub",
    ] + glob(["**/*.in"]),
    outs = ["config.h"],
    cmd = "./$(location configure) " + 
          "&& cp config.h $(location config.h)",
)

cc_library(
    name = "liblame",
    srcs = glob([
        "libmp3lame/*.c",
        "libmp3lame/vector/*.c",
        "mpglib/*.c",
    ]),
    hdrs = glob([
        "include/*.h",
        "libmp3lame/*.h",
        "libmp3lame/vector/*.h",
        "mpglib/*.h",
    ]) + [
        "config.h",
    ],
    copts = ["-Wno-sign-compare -DHAVE_CONFIG_H"],
    includes = ["include", "libmp3lame", "mpglib", "."],
    visibility = ["//visibility:public"],
)
