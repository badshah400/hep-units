project('hep-units', version: '0.1', meson_version: '>= 1.3.0')

maxima = find_program('maxima', required: true)
maxima_version = maxima.version()
message(
    'Found maxima version ' + maxima_version + ' at ' + maxima.full_path() + '.',
)

user_install = get_option('user')
if user_install
    fs = import('fs')
    prefix = fs.expanduser('~')
    datadir = prefix / '.maxima'
else
    prefix = get_option('prefix')
    datadir = prefix / get_option('datadir') / 'maxima' / maxima_version / 'share'
endif

maxima_package_dir = datadir / meson.project_name()
install_data('src/hep_units.wxm', install_dir: maxima_package_dir)
