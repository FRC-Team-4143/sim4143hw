project(sim4143hw)

#include(CompileWarnings)

file(GLOB sim4143hw_src src/main/native/cpp/*.cpp)

add_library(sim4143hw SHARED ${sim4143hw_src})
#wpilib_target_warnings(sim4143hw)
set_target_properties(sim4143hw PROPERTIES DEBUG_POSTFIX "d")
target_link_libraries(sim4143hw PUBLIC wpiHal wpiutil)

target_include_directories(sim4143hw PRIVATE src/main/native/include /usr/local/include/hal /usr/local/include/wpiutil)

set_property(TARGET sim4143hw PROPERTY FOLDER "libraries")

install(TARGETS sim4143hw EXPORT sim4143hw DESTINATION "${main_lib_dest}")
