include(GNUInstallDirs)

# List of all buildable examples.
set(EXAMPLES
  sample
)

foreach(EXAMPLE ${EXAMPLES})
  # Add example executable.
  add_executable(${EXAMPLE} "")

  # Add example source file.
  target_sources(
    ${EXAMPLE}
    PRIVATE
    ${EXAMPLE}.cpp
  )

  # Link example with the library.
  target_link_libraries(${EXAMPLE} beman.iterator_interface)

  # Install .
  install(
    TARGETS ${EXAMPLE}
    EXPORT ${TARGETS_EXPORT_NAME}
    DESTINATION ${CMAKE_INSTALL_BINDIR}
  )
endforeach()
