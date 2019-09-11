set(headers
    include/Boolean.hh
    include/HashTable.hh
    include/UsageEnvironment.hh
    include/UsageEnvironment_version.hh
    include/strDup.hh
)
add_library(UsageEnvironment OBJECT
    ${headers}
    HashTable.cpp
    UsageEnvironment.cpp
    strDup.cpp
)
target_include_directories(UsageEnvironment
    PUBLIC
        $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
        # This is a cyclic dependency :(
        $<BUILD_INTERFACE:${live555_SOURCE_DIR}/groupsock/include>
)