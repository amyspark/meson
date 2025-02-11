dep2sources = ['dep2.c', 'dep2.h']

dep2lib = shared_library(
  'dep2lib',
  sources : dep2sources,
  dependencies : gobj,
  vs_module_defs: 'dep2.def',
  install : true
)

envdata.append('GI_TYPELIB_PATH', dep2lib.outdir())
envdata.append(var, dep2lib.outdir())

dep2gir = gnome.generate_gir(
  dep2lib,
  sources : dep2sources,
  env : envdata,
  nsversion : '1.0',
  namespace : 'MesonDep2',
  symbol_prefix : 'meson',
  identifier_prefix : 'Meson',
  includes : ['GObject-2.0'],
  install : true
)

dep2_dep = declare_dependency(link_with : dep2lib,
  sources : [dep2gir])
