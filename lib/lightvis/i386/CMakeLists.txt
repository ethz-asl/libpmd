remake_add_files(
  * EXCLUDE lightvis
  INSTALL ${CMAKE_INSTALL_PREFIX}/${LIBPMD_LIBRARY_DESTINATION}/pmd/lightvis
)
remake_add_scripts(
  lightvis PREFIX OFF
  INSTALL ${CMAKE_INSTALL_PREFIX}/${LIBPMD_LIBRARY_DESTINATION}/pmd/lightvis
)
