project('sqlite', 'c',
          version : '3.29.0',
          license : 'pd',
    meson_version : '>= 0.48.0'
)

cc = meson.get_compiler('c')
dl_dep = cc.find_library('dl', required: false)

thread_dep = dependency('threads')

inc = include_directories('.')

sqlite = static_library('sqlite3',
  'sqlite3.c',
  include_directories : inc,
         dependencies : [thread_dep, dl_dep],
              install : false
)

sqlite_dep = declare_dependency(
  include_directories : inc,
            link_with : sqlite,
              version : meson.project_version()
)
