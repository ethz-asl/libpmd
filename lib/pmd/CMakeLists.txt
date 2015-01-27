if(CMAKE_SIZEOF_VOID_P EQUAL 8)
  remake_add_directories(amd64)
else()
  remake_add_directories(i386)
endif()

remake_pkg_config_generate(EXTRA_LIBS -lpmdaccess2)
