shader_gen_h = custom_target(
    'shader_gen_h',
    output: 'shader.gen.h',
    input: 'shader.glsl',
    command: [osd_stringify, '@INPUT@', '@OUTPUT@'],
)

shader_gl3_gen_h = custom_target(
    'shader_gl3_gen_h',
    output: 'shader_gl3.gen.h',
    input: 'shader_gl3.glsl',
    command: [osd_stringify, '@INPUT@', '@OUTPUT@'],
)

executable(
    'glViewer',
    [
        'glViewer.cpp',
        shader_gen_h,
        shader_gl3_gen_h,
    ],
    install: true,
    dependencies: [
        glLoader_dep,
        opensubdiv_dep,
        common_gl_dep,
        regression_common_dep,
        regression_far_utils_dep,
    ],
)

