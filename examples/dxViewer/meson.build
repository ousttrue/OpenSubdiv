shader_gen_h = custom_target(
    'shader_gen_h',
    output: 'shader.gen.h',
    input: 'shader.hlsl',
    command: [osd_stringify, '@INPUT@', '@OUTPUT@'],
)

executable(
    'dxViewer',
    ['dxviewer.cpp', shader_gen_h],
    gui_app: true,
    dependencies: [
        common_dx11_dep,
        opensubdiv_dep,
        regression_common_dep,
    ],
    install: true,
)
