cmake_minimum_required(VERSION 3.10)
project(regamedll CXX)

if (WIN32)
	add_custom_target(appversion
		COMMAND cmd /c "${PROJECT_SOURCE_DIR}/regamedll/msvc/PreBuild.bat" "${PROJECT_SOURCE_DIR}/regamedll/version/" "${PROJECT_SOURCE_DIR}/regamedll/")
else()
	add_custom_target(appversion DEPENDS
		COMMAND "${PROJECT_SOURCE_DIR}/regamedll/version/appversion.sh" "${PROJECT_SOURCE_DIR}"
	)
endif()

add_subdirectory(regamedll)
