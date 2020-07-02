include(FindProtobuf)
find_package(Protobuf REQUIRED)

find_package(TensorflowCC REQUIRED)

add_executable(tf_trajectories_example tf_trajectories_example.cc tf_trajectories.cc ${OPEN_SPIEL_OBJECTS}
               $<TARGET_OBJECTS:tests>)
add_test(tf_trajectories_example tf_trajectories_example)

target_link_libraries(tf_trajectories_example ${PROTOBUF_LIBRARIES} TensorflowCC::TensorflowCC)
