set(swift_stdlib_unittest_compile_flags)

add_swift_library(swiftRuntimeUnittest ${SWIFT_STDLIB_LIBRARY_BUILD_TYPES} IS_STDLIB
  # This file should be listed the first.  Module name is inferred from the
  # filename.
  RuntimeUnittest.swift

  ExclusivityTests.cpp

  SWIFT_MODULE_DEPENDS StdlibUnittest
  SWIFT_MODULE_DEPENDS_LINUX Glibc
  SWIFT_MODULE_DEPENDS_FREEBSD Glibc
  SWIFT_MODULE_DEPENDS_CYGWIN Glibc
  SWIFT_MODULE_DEPENDS_HAIKU Glibc
  SWIFT_COMPILE_FLAGS ${swift_stdlib_unittest_compile_flags}
  TARGET_SDKS ALL_POSIX_PLATFORMS
  INSTALL_IN_COMPONENT stdlib-experimental)

