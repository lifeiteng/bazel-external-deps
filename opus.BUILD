licenses(["notice"])

genrule(
    name = "config_h",
    srcs = [
        "autogen.sh",
        "configure.ac",
    ] + glob(["**/*.in", "m4/*.m4"]),
    outs = ["config.h"],
    cmd = "./$(location autogen.sh) " + 
          "&& ./`dirname $(location autogen.sh)`/configure " +
          "&& cp config.h $(location config.h)",
)

cc_library(
    name = "libopus",
    srcs = glob(
        [
            "src/*.c",
            "celt/*.c",
            "silk/*.c",
            "silk/float/*.c",
        ],
        exclude = [
            "celt/opus_custom_demo.c",
            "src/opus_demo.c",
            "src/repacketizer_demo.c",
        ],
    ),
    hdrs = glob(
        [
            "include/*.h",
            "celt/*.h",
            "silk/*.h",
            "silk/float/*.h",
            "src/*.h",
        ],
    ) + [
        "config.h",
    ],
    copts = ["-Wno-sign-compare -DHAVE_CONFIG_H"],
    includes = ["include", "src", "silk/float", "silk", "celt", "."],
    visibility = ["//visibility:public"],
)
