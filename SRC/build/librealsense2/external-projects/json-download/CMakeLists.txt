cmake_minimum_required(VERSION 3.6)
project(nlohmann-json-download NONE)

include(ExternalProject)
ExternalProject_Add(
    nlohmann_json
    PREFIX .
    GIT_REPOSITORY "https://github.com/nlohmann/json.git"
    GIT_TAG        v3.11.3
    GIT_CONFIG     advice.detachedHead=false  # otherwise we'll get "You are in 'detached HEAD' state..."
    SOURCE_DIR     "/home/host/dev_ws/autobot/src/build/librealsense2/third-party/json"
    GIT_SHALLOW    1        # No history needed (requires cmake 3.6)
    # Override default steps with no action, we just want the clone step.
    CONFIGURE_COMMAND ""
    BUILD_COMMAND ""
    INSTALL_COMMAND ""
    )


