cmake_minimum_required(VERSION 2.8)

include("cmake/HunterGate.cmake")
HunterGate(
	URL "https://codeload.github.com/Bjoe/hunter/legacy.zip/288c6e47425ec4eae1a18e9097f7c6e9ac5394ca"
	SHA1 "359e98725698ad25d84b9fa88082d91425f4e5ec"
	LOCAL
)

project(macchina-example-bundle)

hunter_add_package(PocoCpp)
hunter_add_package(macchina)

list(APPEND CMAKE_PREFIX_PATH "${MACCHINA_ROOT}/lib/cmake/macchina")

find_package(MacchinaOSP)

add_library(com.example.samples.service SHARED src/ServiceListener.cpp)
target_include_directories(com.example.samples.service PUBLIC include)
target_link_libraries(com.example.samples.service PUBLIC Poco::OSP)

create_bundle(TARGET com.example.samples.service SPEC_FILE ExampleService.bndlspec)
