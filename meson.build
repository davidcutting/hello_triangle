project(
    'hello_triangle_example',
    'cpp',
    version : '0.0.1',
    license: 'MIT',
    default_options : [
        'cpp_std=c++20',
        'buildtype=debug',
        'warning_level=3'
    ]
)

project_description = 'A HelloTriangle example using the String engine.'

build_args = [
]

# --------------------------------------------------

# ======
# Target
# ======

src = [
    'src/sandbox_app.cpp'
]

deps = [
    dependency('string', static : false)
]

build_args += [
    '-DPROJECT_NAME=' + meson.project_name(),
    '-DPROJECT_VERSION=' + meson.project_version()
]

hello_triangle_example = executable(
    meson.project_name(),
    dependencies: deps,
    sources : src,
    install : true,
    cpp_args : build_args
)

pkg_mod = import('pkgconfig')
pkg_mod.generate(
    name : meson.project_name(),
    filebase : meson.project_name(),
    description : project_description,
    subdirs : meson.project_name(),
)