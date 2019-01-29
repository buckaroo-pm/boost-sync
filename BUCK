load('//:buckaroo_macros.bzl', 'buckaroo_deps')
load('//:subdir_glob.bzl', 'subdir_glob')

posix_srcs = [
  'src/tss_pthread.cpp',
]

windows_srcs = [
  'src/tss_windows.cpp',
  'src/tss_windows_dll.cpp',
  'src/tss_windows_hooks.cpp',
  'src/tss_windows_pe.cpp',
]

cxx_library(
  name = 'sync',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('include', '**/*.hpp'),
  ]),
  headers = subdir_glob([
    ('src', '**/*.hpp'),
  ]),
  platform_srcs = [
    ('linux.*', posix_srcs),
    ('macos.*', posix_srcs),
    ('windows.*', posix_srcs),
  ],
  deps = buckaroo_deps(),
  visibility = [
    'PUBLIC',
  ],
)
