set(PLUGIN_NAME ComposeOptical)
set(PLUGIN_VENDOR DWANGO)

set(SOURCES
	src/main.cpp)

add_library(${PLUGIN_NAME} SHARED ${HEADERS} ${SOURCES} )

set_target_properties(${PLUGIN_NAME} PROPERTIES
	PREFIX "${PLUGIN_VENDOR}_"
	SUFFIX ".plugin"
	ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../lib"
	LIBRARY_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../lib"
	RUNTIME_OUTPUT_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/../bin")

add_definitions(-DPLUGIN_NAME="${PLUGIN_NAME}")
add_definitions(-DPLUGIN_VENDOR="${PLUGIN_VENDOR}")

target_link_libraries(${PLUGIN_NAME} ${LIBS})
