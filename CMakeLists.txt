cmake_minimum_required(VERSION 3.16)
project(atidaq)

add_library(atidaq
        ATIDAQ/ftconfig.c
        ATIDAQ/ftrt.c
        ATIDAQ/dom.c
        ATIDAQ/expatls.c
        ATIDAQ/node.c
        ATIDAQ/stack.c
        ATIDAQ/xmlparse.c
        ATIDAQ/xmlrole.c
        ATIDAQ/xmltok.c
)

target_include_directories(atidaq PUBLIC ATIDAQ)

add_executable(calinfo Samples/calinfo.c)
link_libraries(calinfo PRIVATE atidaq)

add_executable(ftconvert Samples/ftconvert.c)
link_libraries(ftconvert PRIVATE atidaq)