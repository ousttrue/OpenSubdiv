subdir('sdc')
subdir('vtr')
subdir('far')
subdir('osd')

opensubdiv_lib = static_library(
    'opensubdiv',
    ['version.cpp'],
    dependencies: [sdc_dep, vtr_dep, far_dep, osd_dep],
)
opensubdiv_dep = declare_dependency(
    include_directories: opensubdiv_inc,
    link_with: opensubdiv_lib,
    compile_args: [
        '-DOPENSUBDIV_VERSION_STRING="' + meson.project_version() + '"',
    ],
)
