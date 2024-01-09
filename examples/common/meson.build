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
    'examples_common_dx11',
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

glfw_dep = dependency('glfw3', default_options: ['install=true'])

common_gl_lib = static_library(
    'examples_common_gl',
    common + [
        'glControlMeshDisplay.cpp',
        'glHud.cpp',
        'glUtils.cpp',
        'glShaderCache.cpp',
    ],
    dependencies: [
        opensubdiv_dep,
        glLoader_dep,
        glfw_dep,
    ],
)

common_gl_dep = declare_dependency(
    link_with: common_gl_lib,
    dependencies: [glfw_dep],
)


