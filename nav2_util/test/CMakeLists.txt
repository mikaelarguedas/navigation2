ament_add_gtest(test_execution_timer test_execution_timer.cpp)

ament_add_gtest(test_node_utils test_node_utils.cpp)
target_link_libraries(test_node_utils ${library_name})

find_package(std_srvs)

ament_add_gtest(test_service_client test_service_client.cpp)
ament_target_dependencies(test_service_client std_srvs)
target_link_libraries(test_service_client ${library_name})

ament_add_gtest(test_string_utils test_string_utils.cpp)
target_link_libraries(test_string_utils ${library_name})

find_package(rclcpp_lifecycle REQUIRED)
ament_add_gtest(test_lifecycle_utils test_lifecycle_utils.cpp)
ament_target_dependencies(test_lifecycle_utils rclcpp_lifecycle)
target_link_libraries(test_lifecycle_utils ${library_name})

ament_add_gtest(test_actions test_actions.cpp)
ament_target_dependencies(test_actions rclcpp_action test_msgs)
target_link_libraries(test_actions ${library_name})
