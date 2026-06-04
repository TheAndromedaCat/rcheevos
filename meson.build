project('rcheevos', 'c', default_options: ['default_library=static'])

cc = meson.get_compiler('c')
m_dep = cc.find_library('m', required: false)

rcheevos_inc = include_directories('include', 'src')

rcheevos_sources = files(
  'src/rc_client_external.c',
  'src/rc_client_raintegration.c',
  'src/rc_client.c',
  'src/rc_compat.c',
  'src/rc_libretro.c',
  'src/rc_util.c',
  'src/rc_version.c',
  'src/rapi/rc_api_common.c',
  'src/rapi/rc_api_editor.c',
  'src/rapi/rc_api_info.c',
  'src/rapi/rc_api_runtime.c',
  'src/rapi/rc_api_user.c',
  'src/rcheevos/alloc.c',
  'src/rcheevos/condition.c',
  'src/rcheevos/condset.c',
  'src/rcheevos/consoleinfo.c',
  'src/rcheevos/format.c',
  'src/rcheevos/lboard.c',
  'src/rcheevos/memref.c',
  'src/rcheevos/operand.c',
  'src/rcheevos/rc_validate.c',
  'src/rcheevos/richpresence.c',
  'src/rcheevos/runtime.c',
  'src/rcheevos/runtime_progress.c',
  'src/rcheevos/trigger.c',
  'src/rcheevos/value.c',
  'src/rhash/aes.c',
  'src/rhash/cdreader.c',
  'src/rhash/hash.c',
  'src/rhash/hash_disc.c',
  'src/rhash/hash_encrypted.c',
  'src/rhash/hash_rom.c',
  'src/rhash/hash_zip.c',
  'src/rhash/md5.c',
)

rcheevos_lib = static_library(
  'rcheevos',
  sources: rcheevos_sources,
  include_directories: rcheevos_inc,
  dependencies: [m_dep],
  c_args: ['-DRC_DISABLE_LUA', '-DRC_CLIENT_SUPPORTS_HASH'],
  build_by_default: false,
)

rcheevos_dep = declare_dependency(
  include_directories: rcheevos_inc,
  link_with: rcheevos_lib,
  dependencies: [m_dep],
)
