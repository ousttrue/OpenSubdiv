glLoader_args = [
    '-DOSD_USES_INTERNAL_GLAPILOADER=1',
]
glLoader_lib = static_library(
    'glLoader',
    [
        'glLoader.cpp',
        'glApi.cpp',
    ],
    cpp_args: glLoader_args,
)
glLoader_dep = declare_dependency(
    link_with: glLoader_lib,
    include_directories: include_directories('.'),
    compile_args: glLoader_args,
)
