project('cLDtk', 'c',
    version : '1.0.0',
    license : 'MIT',
    meson_version : '>=1.1.0',
    default_options : [
        'c_std=c99', 'optimization=2',
        'warning_level=2'
        ]
)

# cLDtk depends on the parson JSON library, which
# we have as a git submodule and is built as a Meson 
# subproject.
parson_subproj = subproject('parson')
parson_dep = parson_subproj.get_variable('parson')
parson_lib = parson_subproj.get_variable('parson_lib')
parson_inc = parson_subproj.get_variable('parson_inc')

cLDtk_sources = ['src/cLDtk.c']
cLDtk_inc = include_directories('include')

cLDtk_lib = library(
    meson.project_name(),
    sources: cLDtk_sources,
    include_directories: [cLDtk_inc, parson_inc],
    dependencies: parson_dep,
    install: true
)

install_headers('include/cLDtk/cLDtk.h')

cLDtk = declare_dependency(
    include_directories: [cLDtk_inc, parson_inc],
    link_with: cLDtk_lib,
    dependencies: parson_dep
)

pkgconfig = import('pkgconfig')

# will create a pkg config
pkgconfig.generate(cLDtk_lib,
    version: meson.project_version(),
    filebase: meson.project_name(),
    name: meson.project_name(),
    description: 'C loader for the LDtk map editor.',
)

subdir('examples')
