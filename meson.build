# -*- mode: python; -*-

project(
    'tinyendian',
    'd',
    meson_version: '>=0.41',
    version: '0.2.0',
    default_options: ['buildtype=release'],
)

src_dir = include_directories('source/')
pkgc = import('pkgconfig')

tinyendian_src = [
    'source/tinyendian.d'
]

install_headers(tinyendian_src, subdir: 'd/')

tinyendian_lib = library(
    meson.project_name(),
    [tinyendian_src],
    include_directories: [src_dir],
    version: meson.project_version(),
    pic: true,
    install: true,
)

pkgc.generate(
    name: meson.project_name(),
    libraries: tinyendian_lib,
    subdirs: 'd/',
    version: meson.project_version(),
    description: 'Lightweight endianness library for D.'
)

# Make Tinyendian easy to use as subproject
tinyendian_dep = declare_dependency(
    link_with: tinyendian_lib,
    include_directories: [src_dir]
)
