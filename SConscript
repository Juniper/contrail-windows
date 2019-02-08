env = DefaultEnvironment().Clone()

vpath = '#windows/src'

env.AppendUnique(CCFLAGS=['/DUNICODE', '/D_UNICODE']) # both are needed by the compiler
env.Append(CPPPATH = '#build/include')

#env.VariantDir('#/' + Dir('.').path + '/src', vpath, duplicate=0)
buildpath = Dir('.').abspath + '/src'

files = Glob(buildpath + '/misc/*.cc') + [
    buildpath + '/isc/hmacsha.cc',
    buildpath + '/sys/eventfd.cc',
    buildpath + '/sys/ioctl.cc',
    buildpath + '/sys/resource.cc',
    buildpath + '/sys/time.cc',
    buildpath + '/sys/wait.cc',
    buildpath + '/posix_fcntl.cc',
    buildpath + '/posix_stdlib.cc',
    buildpath + '/posix_string.cc',
    buildpath + '/posix_time.cc',
    buildpath + '/endian.cc',
    buildpath + '/sched.cc',
    buildpath + '/strings.cc',
    buildpath + '/unistd.cc',
    buildpath + '/wmiutils.cc'
]

contrail_windows_lib = env.Library('contrail-windows', files)
env.Requires(contrail_windows_lib, '#build/include/boost')
env.Install('#build/lib', 'contrail-windows.lib')
env.Alias('contrail_windows', '#/build/lib/contrail-windows.lib')
