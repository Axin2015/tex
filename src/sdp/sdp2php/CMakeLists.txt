INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR}/src)

ADD_EXECUTABLE(sdp2php sdp2php.cpp)
TARGET_LINK_LIBRARIES(sdp2php parse)

INSTALL(TARGETS sdp2php DESTINATION bin EXPORT mfw-libs)

ADD_SUBDIRECTORY(sdpphp)
ADD_SUBDIRECTORY(php)
