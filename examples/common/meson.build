common_dx11_inc = include_directories('.')

common = [
    'font_image.cpp',
    'hdr_reader.cpp',
    'hud.cpp',
    'objAnim.cpp',
    'patchColors.cpp',
    'viewerArgsUtils.cpp',
]

common_dx11_lib = static_library(
    'examples_common_dx11_obj',
    common + [
        'd3d11ControlMeshDisplay.cpp',
        'd3d11Hud.cpp',
        'd3d11Utils.cpp',
        'd3d11ShaderCache.cpp',
    ],
    include_directories: common_dx11_inc,
    dependencies: [opensubdiv_dep],
)

cxx = meson.get_compiler('cpp')
d3d11 = cxx.find_library('d3d11', required: true)
d3dcompiler = cxx.find_library('d3dcompiler', required: true)
d3d11_dep = declare_dependency(
    dependencies: [d3d11, d3dcompiler],
)

common_dx11_dep = declare_dependency(
    include_directories: common_dx11_inc,
    link_with: common_dx11_lib,
    dependencies: [d3d11_dep],
)
