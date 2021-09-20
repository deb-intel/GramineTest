common_src = files(
    'avl_tree.c',
    'network/hton.c',
    'network/inet_pton.c',
    'path.c',
    'stack_protector.c',
    'stdlib/printfmt.c',
    'string/atoi.c',
    'string/ctype.c',
    'string/memcmp.c',
    'string/memcpy.c',
    'string/memset.c',
    'string/strchr.c',
    'string/strcmp.c',
    'string/strlen.c',
    'string/strspn.c',
    'string/strstr.c',
    'string/toml_utils.c',
    'string/utils.c',
)
if asan
    common_src += files('asan.c')
endif
if ubsan
    common_src += files('ubsan.c')
endif

common_dep = declare_dependency(
    sources: common_src,

    include_directories: common_inc,

    dependencies: [
        uthash_dep,
        tomlc99_dep,
    ],
)