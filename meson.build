project('dependency', ['c'],
  default_options: ['werror=true', 'buildtype=debugoptimized'],
  version: '0.0.1',
)

incs = include_directories('include')

srcs = files(
  'src/dependency.c',
)

host = build_machine.system()
if host == 'windows'
  args = ['-DBUILD_SHARED_LIB']
  so_version = ''
else
  args = []
  so_version = 0
endif

libdependency = library('dependency', srcs,
  include_directories: incs,
  c_args: args,
  install: true,
  install_rpath: '$ORIGIN',
  soversion: so_version,
  version: meson.project_version(),
)

libdependency_dep = declare_dependency(
  include_directories: incs,
  link_with: libdependency,
)
