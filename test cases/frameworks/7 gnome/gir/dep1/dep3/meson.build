dep3sources = ['dep3.c', 'dep3.h']

dep3lib = shared_library(
  'dep3lib',
  sources : dep3sources,
  dependencies : gobj,
  vs_module_defs: 'dep3.def',
  install : true
)

envdata.append('GI_TYPELIB_PATH', dep3lib.outdir())
envdata.append(var, dep3lib.outdir())

dep3gir = gnome.generate_gir(
  dep3lib,
  sources : dep3sources,
  env : envdata,
  nsversion : '1.0',
  namespace : 'MesonDep3',
  symbol_prefix : 'meson',
  identifier_prefix : 'Meson',
  includes : ['GObject-2.0'],
  install : true
)

dep3_dep = declare_dependency(link_with : dep3lib,
  sources : [dep3gir])
