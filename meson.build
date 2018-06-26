project('tinyendian', 'd',
    meson_version: '>=0.40',
    version: '0.2.0'
)

project_soversion    = '0'

src_dir = include_directories('source/')
pkgc = import('pkgconfig')

tinyendian_src = [
    'source/tinyendian.d'
]
install_headers(tinyendian_src, subdir: 'd/')

tinyendian_lib = library('tinyendian',
        [tinyendian_src],
        include_directories: [src_dir],
        install: true,
        version: meson.project_version(),
        soversion: project_soversion,
        pic: true
)
pkgc.generate(name: 'tinyendian',
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
