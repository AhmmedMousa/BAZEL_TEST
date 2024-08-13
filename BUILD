# ####### Your code starts here #######
	
# define the package visibility as public to be able to use it in external repo
visibility("public")

# load the string_build_setting target from def.bzl
load("//Bazel_Exercise/Bazel_stringLib/def.bzl")

# #######  Your code ends here  #######

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

# ####### Your code starts here #######
	
# define two config setting based on the select attr above and provide value for actor-name as "actor" and for hero-name as "hero"

config_setting {
name = "actor-name" ,
constraint_value = {":actor"},
}

config_setting {
name = "hero-name" ,
constraint_value = {":hero"},
}

constraint_setting(name = "type")
constraint_value(name = "actor",constraint_setting = "type")
constraint_value(name = "hero",constraint_setting = "type")


# #######  Your code ends here  #######
