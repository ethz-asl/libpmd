cmake_minimum_required(VERSION 2.6)

include(ReMake)

remake_project(
  libpmd
  VERSION 2.0
  RELEASE stable
  SUMMARY "Driver library for the PMD Technologies GmbH Argos3D P100 ToF camera."
  AUTHOR "PMD Technologies GmbH"
  CONTACT "support@bluetechnix.com"
  HOME "https://support.bluetechnix.at/wiki/PMDSDK_/_PMDMDK_User_Manual"
  LICENSE "MIT License (MIT)"
  README README.md
  PREFIX pmd-
  INSTALL /usr
  CONFIGURATION_DESTINATION /etc/pmd
  HEADER_DESTINATION include/pmd
)

remake_add_directories(lib)
remake_component(
  udev
  CONFIGURATION_DESTINATION /etc/udev
)
remake_add_directories(
  rules
  COMPONENT udev
)
remake_doc(
  vendor
  html
)

remake_pack_deb(
)
remake_pack_deb(
  COMPONENT utils
  DESCRIPTION "utilities"
  DEPENDS libpmd
)
remake_pack_deb(
  COMPONENT dev
  DESCRIPTION "development headers"
  DEPENDS libpmd
)
remake_pack_deb(
  COMPONENT udev
  DESCRIPTION "udev rules"
  DEPENDS udev
  EXTRA debian/rules/*
)
remake_pack_deb(
  ARCH all
  COMPONENT doc
  DESCRIPTION "documentation"
)

remake_distribute_deb(
  DISTRIBUTION precise
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS remake doxygen pkg-config
  PASS CMAKE_BUILD_TYPE LIBPMD_GIT_REVISION
)
remake_distribute_deb(
  DISTRIBUTION trusty
  SECTION libs
  UPLOAD ppa:kralf/asl
  DEPENDS remake doxygen pkg-config
  PASS CMAKE_BUILD_TYPE LIBPMD_GIT_REVISION
)
