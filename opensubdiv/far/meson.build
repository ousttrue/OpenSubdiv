far_lib = static_library(
    'far',
    [
        'bilinearPatchBuilder.cpp',
        'catmarkPatchBuilder.cpp',
        'error.cpp',
        'loopPatchBuilder.cpp',
        'patchBasis.cpp',
        'patchBuilder.cpp',
        'patchDescriptor.cpp',
        'patchMap.cpp',
        'patchTable.cpp',
        'patchTableFactory.cpp',
        'ptexIndices.cpp',
        'stencilTable.cpp',
        'stencilTableFactory.cpp',
        'stencilBuilder.cpp',
        'topologyDescriptor.cpp',
        'topologyRefiner.cpp',
        'topologyRefinerFactory.cpp',
    ],
)
far_dep = declare_dependency(
    link_with: far_lib,
)
