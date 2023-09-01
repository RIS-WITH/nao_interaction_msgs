cmake_minimum_required(VERSION 3.0.2)
project(nao_interaction_msgs)

find_package(catkin REQUIRED COMPONENTS
  actionlib_msgs
  geometry_msgs
  message_generation
  nav_msgs
  sensor_msgs
  std_msgs
  trajectory_msgs
)

## Generate messages in the 'msg' folder
add_message_files(
  FILES
  #~ generic
  Floats32.msg
  #~ nao_vision
  FaceDetected.msg 
  FaceDetectedArray.msg 
  MovementDetected.msg 
  LandmarkDetected.msg 
  PersonDetected.msg
  PersonDetectedArray.msg
  ExpressionProperties.msg
  FaceInfo.msg
  GazeInfo.msg
  PersonInfo.msg
  #~ nao_audio
  AudioSourceLocalization.msg
  BatteryInfo.msg
  RechargeStatus.msg
  Path.msg
)

## Generate services in the 'srv' folder
add_service_files(
  FILES
  #~ nao_vision
  VisionMotionSensitivity.srv
  LearnFace.srv
  # #~ nao_audio
  AudioRecorder.srv
  AudioMasterVolume.srv
  AudioPlayback.srv
  BehaviorManagerInfo.srv
  BehaviorManagerControl.srv
  SetTrackerTarget.srv
  SetTrackerMode.srv
  StartTracker.srv
  TrackerPointAt.srv
  TrackerLookAt.srv
  SetBreathEnabled.srv
  LocalizationTrigger.srv
  LocalizationTriggerString.srv
  LocalizationCheck.srv
  LocalizationGetErrorMessage.srv
  Say.srv
  GoToPosture.srv
  GoToPose.srv
  Explore.srv
  LoadExploration.srv
  RelocalizeInMap.srv
  Recharge.srv
  RechargeReturnPose.srv
  SetExternalCollision.srv
  GetRobotPositionInMap.srv
  SetMoveArmsEnabled.srv
  FollowPath.srv
  String.srv
  MotionInterpolate.srv
  MotionSetAngles.srv
  Float.srv
  Int.srv
  LedsCreateGroup.srv
  LedsEarSetAngle.srv
  LedsFadeRGB.srv
  LedsFade.srv
  LedsList.srv
  LedsRotateEyes.srv
  LedsSetIntensity.srv
)

## Generate actions in the 'action' folder
add_action_files(
  FILES
  NavigateTo.action
)

## Generate added messages and services with any dependencies listed here
generate_messages(
  DEPENDENCIES
  actionlib_msgs
  geometry_msgs
  nav_msgs
  sensor_msgs
  std_msgs
  trajectory_msgs
)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES nao_interaction_msgs
 CATKIN_DEPENDS actionlib_msgs geometry_msgs nav_msgs sensor_msgs std_msgs trajectory_msgs
#  DEPENDS system_lib
)

