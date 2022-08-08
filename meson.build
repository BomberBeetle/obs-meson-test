project('obs-meson-test', 'c')

obs_dep = dependency('libobs', required : false)
if not obs_dep.found()
  obs_dep = meson.get_compiler('c').find_library('obs', has_headers : 'obs/obs.h')
endif

name_suffix = []
if host_machine.system() == 'darwin'
  name_suffix = 'so'
endif

shared_library('obs-meson-test',
  'plugin-main.c',
  name_prefix : '',
  name_suffix : name_suffix,
  dependencies : [
    obs_dep,
  ],
  install : true,
  install_dir : join_paths(get_option('libdir'), 'obs-plugins'),
)