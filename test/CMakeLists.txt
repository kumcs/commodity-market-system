file(GLOB TEST_SOURCES Test*.cpp)

foreach(TEST_SRC ${TEST_SOURCES})
    get_filename_component (TEST_SRC_NAME ${TEST_SRC} NAME_WE)
    add_executable(${TEST_SRC_NAME} ${TEST_SRC} ${CMS_SRC_DIR})
    target_link_libraries(${TEST_SRC_NAME}
            ${Boost_LIBRARIES})
    add_test(${TEST_SRC_NAME} ${TEST_SRC_NAME})
endforeach(TEST_SRC)

