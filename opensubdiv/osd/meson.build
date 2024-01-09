kernels = [
    'patchBasis.h',
    'patchBasisTypes.h',
    # dx
    'hlslComputeKernel.hlsl',
    'hlslPatchCommon.hlsl',
    'hlslPatchCommonTess.hlsl',
    'hlslPatchBoxSplineTriangle.hlsl',
    'hlslPatchBSpline.hlsl',
    'hlslPatchGregory.hlsl',
    'hlslPatchGregoryBasis.hlsl',
    'hlslPatchGregoryTriangle.hlsl',
    'hlslPatchLegacy.hlsl',
    # gl
    'glslPatchCommon.glsl',
    'glslPatchCommonTess.glsl',
    'glslPatchBoxSplineTriangle.glsl',
    'glslPatchBSpline.glsl',
    'glslPatchGregory.glsl',
    'glslPatchGregoryBasis.glsl',
    'glslPatchGregoryTriangle.glsl',
    'glslPatchLegacy.glsl',
]

gens = []
foreach k : kernels
    sp = k.split('.')
    g = custom_target(
        sp[0] + '_gen_h',
        output: sp[0] + '.gen.h',
        input: k,
        command: [osd_stringify, '@INPUT@', '@OUTPUT@'],
    )
    gens += g
endforeach

osd_inc = include_directories('.')
osd_lib = static_library(
    'osd_obj',
    [
        'cpuEvaluator.cpp',
        'cpuKernel.cpp',
        'cpuPatchTable.cpp',
        'cpuVertexBuffer.cpp',
        # dx
        'cpuD3D11VertexBuffer.cpp',
        'd3d11ComputeEvaluator.cpp',
        'd3d11LegacyGregoryPatchTable.cpp',
        'd3d11PatchTable.cpp',
        'd3d11VertexBuffer.cpp',
        'hlslPatchShaderSource.cpp',
        # gl
        'cpuGLVertexBuffer.cpp',
        'glLegacyGregoryPatchTable.cpp',
        'glPatchTable.cpp',
        'glVertexBuffer.cpp',
        'glslPatchShaderSource.cpp',
    ] + gens,
    dependencies: [
        glLoader_dep,
    ],
)
osd_dep = declare_dependency(
    link_with: osd_lib,
    # include_directories: osd_inc,
)
