macro(optional_add_subdirectory dir)
  option(BUILD_${dir} "Build producer in directory ${dir}?" OFF)
  if(BUILD_${dir} OR BUILD_allproducer)
    add_subdirectory(${dir})
    MESSAGE( STATUS "Building producer: " ${dir} )
  endif()
endmacro()

# set to build all producers -- mostly useful for tests
option(BUILD_allproducer "Build all producers?" OFF)

# some producers do not e.g. run under Windows or have missing includes/dependencies
# with this option set to "ON" they are built anyway
option(IGNORE_KNOWN_ISSUES "Ignore known compilation issues of producer executables and configure them anyway?" OFF)

optional_add_subdirectory(altro)
optional_add_subdirectory(altroUSB)
optional_add_subdirectory(depfet)
optional_add_subdirectory(eudrb)
optional_add_subdirectory(explorer)
optional_add_subdirectory(fortis)
optional_add_subdirectory(mimoroma)
optional_add_subdirectory(mimosa32)
optional_add_subdirectory(mvd)
optional_add_subdirectory(ni)
optional_add_subdirectory(pixelmanproducer)
optional_add_subdirectory(taki)
optional_add_subdirectory(timepixdummy)
optional_add_subdirectory(tlu)
optional_add_subdirectory(miniTLU)
optional_add_subdirectory(timepix3)
