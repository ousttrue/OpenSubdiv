regression_common_lib = static_library(
    'regression_common',
    [
        'arg_utils.cpp',
        'shape_utils.cpp',
    ],
)
regression_common_dep = declare_dependency(
    link_with: regression_common_lib,
)

regression_far_utils_lib = static_library(
    'regression_far_utils',
    [
        'far_utils.cpp',
    ],
    dependencies: [opensubdiv_dep],
)
regression_far_utils_dep = declare_dependency(
    link_with: regression_far_utils_lib,
)

