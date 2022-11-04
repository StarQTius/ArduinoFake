include(git-download)

set(REPO_DIR ${PROJECT_SOURCE_DIR}/${PROJECT_NAME}-repo)

if (${CMAKE_PROJECT_NAME} STREQUAL ArduinoFake)

download_repo(
    URL "https://github.com/ThrowTheSwitch/Unity.git"
    TAG v${PROJECT_VERSION}
    CLONE_DIR ${REPO_DIR}
)

add_library(${PROJECT_NAME} STATIC
    ${REPO_DIR}/src/unity.c
)

target_include_directories(${PROJECT_NAME} PUBLIC
    ${REPO_DIR}/src
)

endif()
