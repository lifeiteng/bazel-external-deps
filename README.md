# bazel-external-deps
example for build automake/autoconf project in bazel project

## generate config.h file

```
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
```

or

```
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
```
