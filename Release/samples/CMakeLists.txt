# Z@2020 port mingw
if(MINGW AND Z_PORT_MINGW)
  set(CMAKE_CXX_LINK_FLAGS "${CMAKE_CXX_LINK_FLAGS} -municode")
  set(CMAKE_CXX_STANDARD_LIBRARIES "${CMAKE_CXX_STANDARD_LIBRARIES} -lgcc -lmsvcr90")
endif()

add_subdirectory(SearchFile)
add_subdirectory(BingRequest)
add_subdirectory(BlackJack)
add_subdirectory(Oauth1Client)
add_subdirectory(Oauth2Client)

add_custom_target(samples
  DEPENDS SearchFile BingRequest blackjackclient blackjackserver oauth1client oauth2client
  )
