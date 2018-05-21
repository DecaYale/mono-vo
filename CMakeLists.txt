cmake_minimum_required(VERSION 2.8)
project( mono-vo )
# find_package( OpenCV 3.0 REQUIRED )
set(OpenCV_DIR "/usr/local/opencv-3.3.0/share/OpenCV")
find_package(OpenCV 3.3 REQUIRED)
include_directories( ${OpenCV_INCLUDE_DIRS} )

file(GLOB viso
    "src/*.h"
    "src/*.cpp"
)
add_executable( vo ${viso} )
target_link_libraries( vo ${OpenCV_LIBS} )
