package(default_visibility = ["//visibility:public"])

load("//:def.bzl", "string_build_setting")

string_build_setting(
    name = "stringJob",
    build_setting_default = "Engineer"
)


cc_library(
	name = "string",
	srcs = select({
		":actor-name" : ["src/string-actor.c"],
		":hero-name"  : ["src/string-hero.c"],
		"//conditions:default" :["src/string.c"],
		}),
	hdrs = ["inc/string.h"],
	includes = ["inc/"],
)

config_setting(
	name = "actor-name",
	flag_values  = { ":stringJob" : "actor" },
)

config_setting(
	name = "hero-name",
	flag_values  = { ":stringJob" : "hero" },
)
