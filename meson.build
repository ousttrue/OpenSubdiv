project(
    'opensubdiv',
    'cpp',
    version: '3.6.0',
    default_options: [],
)

add_project_arguments(
    '-DNOMINMAX',
    '-D_USE_MATH_DEFINES',
    language: 'cpp',
)

opensubdiv_inc = include_directories('.')

subdir('tools/stringify')
subdir('glLoader')
subdir('opensubdiv')
subdir('regression/common')
subdir('examples')

