ADD_EXECUTABLE(annotate annotate.cpp)
ADD_EXECUTABLE(train_shape_model train_shape_model.cpp)
ADD_EXECUTABLE(visualize_shape_model visualize_shape_model.cpp)  
ADD_EXECUTABLE(train_patch_model train_patch_model.cpp) 
ADD_EXECUTABLE(visualize_patch_model visualize_patch_model.cpp)  
ADD_EXECUTABLE(train_face_detector train_face_detector.cpp) 
ADD_EXECUTABLE(visualize_face_detector visualize_face_detector.cpp) 
ADD_EXECUTABLE(train_face_tracker train_face_tracker.cpp) 
ADD_EXECUTABLE(visualize_face_tracker visualize_face_tracker.cpp)

TARGET_LINK_LIBRARIES(annotate ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(train_shape_model ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(visualize_shape_model ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(train_patch_model ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(visualize_patch_model ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(train_face_detector ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(visualize_face_detector ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )
TARGET_LINK_LIBRARIES(train_face_tracker ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} ) 
TARGET_LINK_LIBRARIES(visualize_face_tracker ${OpenCV_LIBS} asmlib ${Boost_LIBRARIES} )

 add_custom_command(TARGET train_face_detector POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_SOURCE_DIR}/../../resources ${EXECUTABLE_OUTPUT_PATH}
    COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_SOURCE_DIR}/../../resources ${EXECUTABLE_OUTPUT_PATH}/Debug
    COMMAND ${CMAKE_COMMAND} -E copy_directory ${CMAKE_CURRENT_SOURCE_DIR}/../../resources ${EXECUTABLE_OUTPUT_PATH}/Release

)