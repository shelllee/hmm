# CMakeList.txt : CMake project for hmm, include source and define
# project specific logic here.
#

# Add source to this project's executable.
file(GLOB ROOT_SOURCE *.cpp)
file(GLOB ROOT_HEADER *.h)

add_executable (hmm ${ROOT_SOURCE} ${ROOT_HEADER})

target_include_directories (hmm PUBLIC
	$<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
	$<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}/dependencies/glm>
	$<INSTALL_INTERFACE:${CMAKE_INSTALL_INCLUDEDIR}>
)

if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET hmm PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
