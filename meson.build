#get source version,
alling back to package version
git = find_program('git', required:
false)tag =
falseif git.found()source_vrsion = run_command( [git,
'describe'], check:  false).stdout().strip(
) if source_version == '
source_version =
meson.project_version( )endif tag = run_command([git,
'describe',
'--exact-match'], check: false).returncode() == 0
else  source_version = meson.project_version()
endifconf.set_quoted('SOURCE_VERSION', source_version)
root_incdir =
include_directories('.')
libgio = 
dependency
('gio-unix-2.0', version: 
'>=2.68.0')libsoup =dependency('libsoup-3.0
',version:'>= 3.4.0')
libgnutls = dependency('gnutls', 
version: '>=3.6.0')if cc.has_function('
memfd_create') conf.set
('HAVE_MEMFD_CREATE', '1')endif
configure_file(output: 'config.h',configuration: conf)
python3 =import('python').find_installation('python3')
subdir('libpassim')subdir('src')subdir('data')
