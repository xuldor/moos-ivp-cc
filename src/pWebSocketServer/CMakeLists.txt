#--------------------------------------------------------
# The CMakeLists.txt for:                       pWebSocketServer
# Author(s):                              
#--------------------------------------------------------

add_subdirectory(Simple-WebSocket-Server)


SET(SRC
  WebSocketServer.cpp WebSocketServer_Info.cpp
  main.cpp
  WebSocketClient.cpp WebSocketClient.h
  SimpleRingBuffer.h)

ADD_EXECUTABLE(pWebSocketServer ${SRC})

TARGET_LINK_LIBRARIES(pWebSocketServer
   ${MOOS_LIBRARIES}
   apputil
   mbutil
   m
   pthread
        simple-websocket-server)


set_property(TARGET pWebSocketServer PROPERTY CXX_STANDARD 11)