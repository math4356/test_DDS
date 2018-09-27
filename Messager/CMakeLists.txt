CMAKE_MINIMUM_REQUIRED(VERSION 3.0)

PROJECT(DDS_TEST)

SET(DDS_INCDIRS /home/xuchang/chang_ws/OpenDDS-3.9
  /home/xuchang/chang_ws/OpenDDS-3.9/test
/home/xuchang/chang_ws/OpenDDS_test/Messager)

SET(ACE_INCDIRS /home/xuchang/chang_ws/OpenDDS-3.9/ACE_wrappers)

INCLUDE_DIRECTORIES(${DDS_INCDIRS} ${ACE_INCDIRS})

SET(DDS_LIBS OpenDDS_Dcps TAO ACE TAO_AnyTypeCode)

SET(ADD_SRC MessengerC.cpp
MessengerTypeSupportC.cpp
MessengerTypeSupportImpl.cpp
DataReaderListenerImpl.cpp)

ADD_EXECUTABLE(Publisher Publisher.cpp ${ADD_SRC})
ADD_EXECUTABLE(Subscriber Subscriber.cpp ${ADD_SRC})

TARGET_LINK_LIBRARIES(Publisher ${DDS_LIBS})
TARGET_LINK_LIBRARIES(Subscriber ${DDS_LIBS})
