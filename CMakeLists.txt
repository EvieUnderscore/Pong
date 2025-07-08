cmake_minimum_required(VERSION 3.11)

project(Pong)

file(GLOB SRC_FILES "src/*.cpp" "src/*.c")

add_executable(${PROJECT_NAME} ${SRC_FILES})


target_link_libraries(${PROJECT_NAME} PRIVATE
    pspdebug
    pspdisplay
    pspge
)

# Create an EBOOT.PBP file
create_pbp_file(
    TARGET ${PROJECT_NAME}
    ICON_PATH "${CMAKE_CURRENT_SOURCE_DIR}/icon.png"
    BACKGROUND_PATH NULL
    PREVIEW_PATH NULL
    TITLE "Pong For PSP"
    VERSION 01.00
)