set(COMPONENT_SRCS
    face_detection/fd_forward.c
    object_detection/object_detection.cpp
    face_recognition/fr_forward.c
    face_recognition/fr_flash.c
    pose_estimation/pe_forward.c
    image_util/image_util.c
    )

set(COMPONENT_ADD_INCLUDEDIRS
    face_detection/include
    face_recognition/include
    object_detection/include
    image_util/include
    pose_estimation/include
    lib/include
    )

set(COMPONENT_REQUIRES spi_flash)

register_component()

target_link_libraries(${COMPONENT_TARGET} "-L ${CMAKE_CURRENT_SOURCE_DIR}/lib")
target_link_libraries(${COMPONENT_TARGET}
    pe
    fd
    fr

    detection_cat_face
    detection

    dl
    )
