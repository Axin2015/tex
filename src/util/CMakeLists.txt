INCLUDE(${PROJECT_SOURCE_DIR}/src/cmake/mysql.cmake)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src/include)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src/3party/utf8)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src/3party/zlib)
INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src/3party/jsoncpp)
AUX_SOURCE_DIRECTORY(${CMAKE_CURRENT_SOURCE_DIR} SOURCE_FILES)
AUX_SOURCE_DIRECTORY(${CMAKE_CURRENT_SOURCE_DIR}/util_impl SOURCE_FILES)

ADD_LIBRARY(util STATIC ${SOURCE_FILES})

INSTALL(TARGETS util DESTINATION lib EXPORT mfw-libs)

FILE(GLOB headers *.h)
INSTALL(FILES ${headers} DESTINATION include/util)
