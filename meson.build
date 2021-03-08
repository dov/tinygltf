# A meson file for the tinygltf library
project('tinygltf','cpp')

inc = include_directories('.','..')
install_headers(['tiny_gltf.h',
                 'stb_image.h',
                 'stb_image_write.h',
                 'json.hpp'],
                 subdir:'tinygltf')

pkg = import('pkgconfig')
pkg.generate(
	version: meson.project_version(),
	name: 'tinygltf',
	filebase: 'tinygltf',
	description: 'A C++ library for gltf files',
)

tinygltf_dep = declare_dependency(
  include_directories : inc)

if meson.version().version_compare('>= 0.54.0')
  meson.override_dependency('tinygltf', tinygltf_dep)
endif
