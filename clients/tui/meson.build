incs = [
  top_inc,
  shared_inc,
  libnm_core_inc
]

deps = [
  glib_dep,
  newt_dep
]

cflags = ['-DG_LOG_DOMAIN="nmtui"']

subdir('newt')

sources = files(
  'nm-editor-bindings.c',
  'nm-editor-utils.c',
  'nmt-address-list.c',
  'nmt-connect-connection-list.c',
  'nmt-device-entry.c',
  'nmt-edit-connection-list.c',
  'nmt-editor.c',
  'nmt-editor-grid.c',
  'nmt-editor-page.c',
  'nmt-editor-page-device.c',
  'nmt-editor-section.c',
  'nmt-ip-entry.c',
  'nmt-mac-entry.c',
  'nmt-mtu-entry.c',
  'nmt-page-bond.c',
  'nmt-page-bridge.c',
  'nmt-page-bridge-port.c',
  'nmt-page-dsl.c',
  'nmt-page-ethernet.c',
  'nmt-page-infiniband.c',
  'nmt-page-ip4.c',
  'nmt-page-ip6.c',
  'nmt-page-ip-tunnel.c',
  'nmt-page-ppp.c',
  'nmt-page-team.c',
  'nmt-page-team-port.c',
  'nmt-page-vlan.c',
  'nmt-page-wifi.c',
  'nmt-password-dialog.c',
  'nmt-password-fields.c',
  'nmt-route-editor.c',
  'nmt-route-entry.c',
  'nmt-route-table.c',
  'nmt-slave-list.c',
  'nmtui.c',
  'nmtui-connect.c',
  'nmtui-edit.c',
  'nmtui-hostname.c',
  'nmt-utils.c',
  'nmt-widget-list.c'
)

deps += [
  libnm_dep,
  libnmc_base_dep,
  libnmt_newt_dep
]

cflags += '-DLOCALEDIR="@0@"'.format(nm_localedir)

ldflags = []
if have_version_script
  ldflags += '-Wl,--version-script,@0@'.format(linker_script_binary)
endif

executable(
  'nmtui',
  sources + [libnm_core_enum[1]],
  include_directories: incs,
  dependencies: deps,
  c_args: cflags,
  link_args: ldflags,
  link_depends: linker_script_binary,
  install: true,
  install_dir: nm_bindir
)
