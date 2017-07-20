# IDLファイル

* [IDL files](https://github.com/fkanehiro/hrpsys-base/tree/master/idl)

# 目次

* [TimedLongSeqSeq](#timedlongseqseq)
* [TimedQuaternion](#timedquaternion)
* [TimedWrench](#timedwrench)
* [TimedSpatialVelocity](#timedspatialvelocity)

### ControlMode

以下の値を列挙。

|名前|説明|
|---|---|
|MODE_IDLE|停止|
|MODE_ZERO_VELOCITY|速度0|
|MODE_RELATIVE_LOCAL_VELOCITY||
|MODE_ABSOLUTE_LOCAL_VELOCITY||
|MODE_RELATIVE_GLOBAL_VELOCITY||
|MODE_ABSOLUTE_GLOBAL_VELOCITY||

### AccelerationFilterParam

|名前|型|説明|単位|
|---|---|---|---|
|gravity|double| |m/s^2|
|use_filter|double| ||
|filter_param|double| ||

### Footstep

|名前|型|説明|単位|
|---|---|---|---|
|pos|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)|足の位置|m|
|rot|[OpenHRP::AutoBalancerService::DblArray4](#DblArray4)|足の姿勢(クォータニオン)||
|leg|string|脚の名前(rlegかlleg)||

### DblArray3

double[3]として定義。

### DblArray4

double[4]として定義。

### Footsteps

|名前|型|説明|単位|
|---|---|---|---|
|fs|sequence< [OpenHRP:AutoBalancerService:::Footstep](#footstep) >|||

### StepParam

|名前|型|説明|単位|
|---|---|---|---|
|step_height|double|遊脚高さ|m|
|step_time|double|遊脚時間|s|
|toe_angle|double|爪先の最大角度|deg|
|heel_angle|double|踵の最大角度|deg|

### StepParams

|名前|型|説明|単位|
|---|---|---|---|
|sps|sequence< [OpenHRP::AutoBalancerService::StepParam](#stepparam) >|||

### SupportLegState

以下の値を列挙。
支持脚の状態を表現。

|名前|説明|
|---|---|
|RLEG|右足|
|LLEG|左足|
|BOTH|両足|

### OrbitType

以下の値を列挙。
遊脚軌道の種類を表現。

|名前|説明|
|---|---|
|SHUFFLING|摺足|
|CYCLOID|サイクロイド曲線|
|RECTANGLE|矩形|
|STAIR||
|CYCLOIDDELAY||
|CYCLOIDDELAYKICK||
|CROSS||

### GaitType

以下の値を列挙。
歩容の種類を表現。

|名前|説明|
|---|---|
|BIPED|二足歩行|
|TROT|トロット歩容|
|PACE|ペース歩容|
|CRAWL|クロール歩容|
|GALLOP|ギャロップ歩容|

### ControllerMode

以下の値を列挙。

|名前|説明|
|---|---|
|MODE_IDLE||
|MODE_ABC||
|MODE_SYNC_TO_IDLE||
|MODE_SYNC_TO_ABC||

### UseForceMode

以下の値を列挙。

|名前|説明|
|---|---|
|MODE_NO_FORCE||
|MODE_REF_FORCE||

### StrideLimitationType

以下の値を列挙。
足先の可動範囲の種類を表現。

|名前|説明|
|---|---|
|SQUARE|立方体|
|CIRCLE|球体|

### FootstepParam

|名前|型|説明|単位|
|---|---|---|---|
|support_leg_coords|[OpenHRP::AutoBalancerService::Footstep](#footstep)|||
|swing_leg_coords|[OpenHRP::AutoBalancerService::Footstep](#footstep)|||
|swing_leg_src_coords|[OpenHRP::AutoBalancerService::Footstep](#footstep)|||
|swing_leg_dst_coords|[OpenHRP::AutoBalancerService::Footstep](#footstep)|||
|dst_foot_midcoords|[OpenHRP::AutoBalancerService::Footstep](#footstep)|||
|support_leg|[OpenHRP::AutoBalancerService::SupportLegState](#supportlegstate)|||
|support_leg_with_both|[OpenHRP::AutoBalancerService::SupportLegState](#supportlegstate)|||

### StrSequence

string型の配列として定義。

### GaitGeneratorParam

|名前|型|説明|単位|
|---|---|---|---|
|default_step_time|double|1歩移動する時間|s|
|default_step_height|double|遊脚高さ|ｍ|
|default_double_support_ratio|double|接地率、デューティ比(0～1)||
|default_double_support_ratio_before|double|||
|default_double_support_ratio_after|double|||
|default_double_support_static_ratio|double|||
|default_double_support_static_ratio_before|double|||
|default_double_support_ratio_swing_after|double|||
|stride_parameter|sequence< double, 4 >|足先の可動範囲(x(前方),y,theta,x(後方))|m,m,deg,m|
|default_orbit_type|[OpenHRP::AutoBalancerService::OrbitType](#orbittype)|遊脚軌道の種類||
|swing_trajectory_delay_time_offset|double| |s|
|swing_trajectory_final_distance_weight|double| ||
|default_orbit_type|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)|||
|swing_trajectory_delay_time_offset|double| |s|
|swing_trajectory_final_distance_weight|double| ||
|stair_trajectory_way_point_offset|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)| |m|
|cycloid_delay_kick_point_offset|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)| |m|
|swing_trajectory_time_offset_xy2z|double| |m|
|gravitational_acceleration|double|重力加速度|m/s^2|
|toe_pos_offset_x|double| |m|
|heel_pos_offset_x|double| |m|
|toe_zmp_offset_x|double| |m|
|heel_zmp_offset_x|double| |m|
|heel_angle|double| |deg|
|toe_check_thre|double| |m|
|heel_check_thre|double| |m|
|toe_heel_phase_ratio|sequence< double >|||
|use_toe_joint|boolean|||
|use_toe_heel_transition|boolean|||
|use_toe_heel_auto_set|boolean|||
|zmp_weight_map|sequence< double, 4 >|||
|leg_default_translate_pos|sequence< [OpenHRP::AutoBalancerService::DblArray3](#dblarray3) >| |m|
|optional_go_pos_finalize_footstep_num|long|||
|overwritable_footstep_index_offset|long|||
|overwritable_stride_limitation|[OpenHRP::AutoBalancerService::DblArray4](#dblarray4)| |m|
|use_stride_limitation|boolean|足先の可動範囲を使用するか？|
|stride_limitation_type|[OpenHRP::AutoBalancerService::StrideLimitationType](#stridelimitationtype)|足先可動範囲の種類||
|leg_margin|[OpenHRP::AutoBalancerService::DblArray4](#dblarray4)|脚先位置の可動範囲までの余裕(前方、後方、外側、内側)|m|

### IKLimbParameters

手足の逆運動学のパラメータを表現。

|名前|型|説明|単位|
|---|---|---|---|
|ik_optional_weight_vector|sequence< double >|||
|sr_gain|double|||
|avoid_gain|double|||
|reference_gain|double|||
|manipulability_limit|double|||

### AutoBalancerParam

|名前|型|説明|単位|
|---|---|---|---|
|default_zmp_offsets|sequence< [OpenHRP::AutoBalancerService::DblArray3](#dblarray3) >| |m|
|move_base_gain|double|||
|controller_mode|[OpenHRP::AutoBalancerService::ControllerMode](#controllermode)|||
|use_force_mode|[OpenHRP::AutoBalancerService::UseForceMode](#useforcemode)|||
|graspless_manip_mode|boolean|||
|graspless_manip_arm|string|||
|graspless_manip_p_gain|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)|||
|graspless_manip_reference_trans_pos|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)| |m|
|graspless_manip_reference_trans_rot|[OpenHRP::AutoBalancerService::DblArray3](#dblarray3)| |rad|
|transition_time|double| |s|
|zmp_transition_time|double| |s|
|adjust_footstep_transition_time|double| |s|
|leg_names|[OpenHRP::AutoBalancerService::StrSequence](#strsequence)|||
|has_ik_failed|boolean|||
|pos_ik_thre|double| |m|
|rot_ik_thre|double| |rad|
|is_hand_fix_mode|boolean|||
|end_effector_list|sequence< [OpenHRP::AutoBalancerService::Footstep](#footstep) >|||
|default_gait_type|[OpenHRP::AutoBalancerService::GaitType](#gaitType)|デフォルトの歩容の種類||
|ik_limb_parameters|sequence< [OpenHRP::AutoBalancerService::IKLimbParameters](#iklimbparameters) >|手足の逆運動学パラメータ||

### CollisionState

接触状態を表現。

|名前|型|説明|単位|
|---|---|---|---|
|time|double|　|s|
|computation_time|double|　|s|
|safe_posture|boolean|　||
|recover_time|double|　|m|
|loop_for_check|short|　||
|angle|sequence< double >|　|rad|
|collide|sequence< boolean >|　||
|lines|sequence< [OpenHRP::CollisionDetectorService::Line](#line) >|　|m|

### Line

[OpenHRP::CollisionDetectorService::DblSequence3](#dblsequence3)型の配列として定義。

### DblSequence3

double型の配列として定義。

### EmergencyStopperParam

|名前|型|説明|単位|
|---|---|---|---|
|default_recover_time|double|　|s|
|default_retrieve_time|double|　|s|
|is_stop_mode|boolean|　||

### ComponentProfile

|名前|型|説明|単位|
|---|---|---|---|
|count|long|　||
|max_process|double|　||
|avg_process|double|　||

### Profile

|名前|型|説明|単位|
|---|---|---|---|
|max_period|double|　||
|min_period|double|　||
|avg_period|double|　||
|max_process|double|　||
|profiles|[OpenHRP::CollisionDetectorService::ComponentProfile](#componentprofile)>|　||
|count|long|　||
|timeover|long|　||

## TimedLongSeqSeq

long型の2次元配列を格納するデータ型。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|sequence< sequence< long > >|データ||

## TimedQuaternion

クォータニオンを格納するデータ型。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|[OpenHRP::Quaternion](#quaternion)>|データ||

### Quaternion

クォータニオンを表現。

|名前|型|説明|単位|
|---|---|---|---|
|x|double|虚部||
|y|double|虚部||
|z|double|虚部||
|w|double|実部||

## TimedWrench

力とトルク値を格納するデータ型。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|[OpenHRP::Wrench](#wrench)>|データ||

### Wrench

力とトルクを表現。

|名前|型|説明|単位|
|---|---|---|---|
|force|[RTC::Vector3D](拡張データ型#vector3d)|力||N|
|torque|[RTC::Vector3D](拡張データ型#vector3d)|トルク||Nm|

## TimedSpatialVelocity

3次元の速度と角速度を格納するデータ型。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|[OpenHRP::SpatialVelocity](#spatialvelocity)>|データ||

### SpatialVelocity

3次元の速度と角速度を表現。

|名前|型|説明|単位|
|---|---|---|---|
|omega|[RTC::AngularVelocity3D](拡張データ型#angularvelocity3d)|角速度||
|vel|[RTC::Velocity3D](拡張データ型#velocity3d)|角度||

### RobotState

|名前|型|説明|単位|
|---|---|---|---|
|name|string|||
|basePose|[RTC::Pose3D](拡張データ型#pose3d)|||
|q|sequence< double >|||

### RobotStateSeq

[OpenHRP::RobotState](#robotstate)型の配列として定義。

### SceneState

|名前|型|説明|単位|
|---|---|---|---|
|time|double|||
|states|[OpenHRP::RobotStateSeq](#robotstateseq)|||

### impedanceParam

インピーダンス制御のパラメータ。

|名前|型|説明|単位|
|---|---|---|---|
|M_p|double|質量|N/(m/s^2)|
|D_p|double|粘性(並進)|N/(m/s)|
|K_p|double|剛性(並進)|[N/m]|
|M_r|double|慣性モーメント|Nm/(rad/s^2)|
|D_r|double|粘性(回転)|N/(rad/s)|
|K_r|double|剛性(回転)|N/rad|
|force_gain|[OpenHRP::ImpedanceControllerService::DblSequence3](#dblsequence3)|||
|moment_gain|[OpenHRP::ImpedanceControllerService::DblSequence3](#dblsequence3)|||
|sr_gain|double|||
|avoid_gain|double|||
|reference_gain|double|||
|manipulability_limit|double|||
|controller_mode|[OpenHRP::ImpedanceControllerService::ControllerMode](#controllermode)|||
|ik_optional_weight_vector|[OpenHRP::ImpedanceControllerService::DblSequence](#dblsequence)|||
|use_sh_base_pos_rpy|boolean|||

### DblSequence

double型の配列として定義。

### Dbl3Sequence

double型の2次元配列として定義。

### objectTurnaroundDetectorParam

|名前|型|説明|単位|
|---|---|---|---|
|wrench_cutoff_freq|double| |Hz|
|dwrench_cutoff_freq|double| |Hz|
|detect_ratio_thre|double| ||
|kf_algorithm|double| ||
|acc_offset|double| |s|
|sensorRPY_offset|double| |s|

### DetectorMode

以下の値を列挙。

|名前|説明|
|---|---|
|MODE_DETECTOR_IDLE||
|MODE_STARTED||
|MODE_DETECTED||
|MODE_MAX_TIME||

### DetectorTotalWrench

以下の値を列挙。

|名前|説明|
|---|---|
|TOTAL_FORCE||
|TOTAL_MOMENT||

### KFAlgorithm

以下の値を列挙。

|名前|説明|
|---|---|
|RPYKalmanFilter||
|QuaternionExtendedKalmanFilter||

### KalmanFilterParam

|名前|型|説明|単位|
|---|---|---|---|
|Q_angle|double| ||
|Q_rate|double| ||
|R_angle|double| ||
|kf_algorithm|double| ||
|acc_offset|double| ||
|sensorRPY_offset|double| ||

### AABB

軸並行境界ボックスを表現。

|名前|型|説明|単位|
|---|---|---|---|
|pos|[RTC::Point3D](拡張データ型#point3d)|x,y,zのいずれかが最小の頂点座標||
|size|[RTC::Size3D](拡張データ型#size3d)|x,y,zの長さ||

### OGMap3D

|名前|型|説明|単位|
|---|---|---|---|
|resolution|double|||
|pos|[RTC::Point3D](拡張データ型#point3d)|||
|nx|double|||
|ny|double|||
|nz|double|||
|cells|[RTC::OGMapCells](拡張データ型#ogmapcells)|||

### ReferenceForceUpdaterParam

|名前|型|説明|単位|
|---|---|---|---|
|motion_dir|[OpenHRP::ReferenceForceUpdaterService::DblSequence3](#dblsequence3)|||
|frame|string||Hz|
|update_freq|double|||
|update_time_ratio|double|||
|p_gain|double|||
|d_gain|double|||
|i_gain|double|||

### forcemomentOffsetParam

|名前|型|説明|単位|
|---|---|---|---|
|force_offset|[OpenHRP::ReferenceForceUpdaterService::DblSequence3](#dblsequence3)| |N|
|moment_offset|[OpenHRP::ReferenceForceUpdaterService::DblSequence3](#dblsequence3)| |Nm|
|link_offset_centroid|[OpenHRP::ReferenceForceUpdaterService::DblSequence3](#dblsequence3)| |m|
|link_offset_mass|double| |kg|

### RobotState

ロボットの状態を表現。

|名前|型|説明|単位|
|---|---|---|---|
|angle|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)|ジョイントの現在の角度|rad|
|command|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)| |rad|
|torque|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)|ジョイントのトルク|Nm|
|link_offset_centroid|[OpenHRP::ReferenceForceUpdaterService::LongSequenceSequence](#longsequencesequence)| |m|
|force|[OpenHRP::RobotHardwareService::DblSequence6](#dblsequence6)|力、トルク|N and Nm|
|rateGyro|[OpenHRP::RobotHardwareService::DblSequence3](#dblsequence3)|角速度|rad/s|
|accel|[OpenHRP::RobotHardwareService::DblSequence3](#dblsequence3)|加速度|m/s^2|
|voltage|double|電圧値|V|
|current|double|電流値|A|

### DblSequence6

double型の配列として定義。

### LongSequenceSequence

[OpenHRP::RobotHardwareService::LongSequence](#longsequence)型の配列として定義。

### LongSequence

long型の配列として定義。

### BatteryState

電源の状態を表現。

|名前|型|説明|単位|
|---|---|---|---|
|voltage|double|電圧値|V|
|current|double|電流値|A|
|soc|double|充電率|%|

### RobotState2

|名前|型|説明|単位|
|---|---|---|---|
|angle|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)|ジョイントの現在の角度|rad|
|command|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)| |rad|
|torque|[OpenHRP::RobotHardwareService::DblSequence](#dblsequence)|ジョイントのトルク|Nm|
|servoState|[OpenHRP::ReferenceForceUpdaterService::LongSequenceSequence](拡張データ型#longsequencesequence)|0番目:モーターキャリブレーションの状態(1で完了)  1番目:サーボの状態(1でオン)  2番目:電源の状態(1で供給されている)  3-18番目:サーボアラーム(iob.h)  19-23番目:未使用  24-31番目：|m|
|force|[OpenHRP::RobotHardwareService::DblSequence6](#dblsequence6)|力、トルク|N and Nm|
|rateGyro|[OpenHRP::RobotHardwareService::DblSequence3](#dblsequence3)|角速度|rad/s|
|accel|[OpenHRP::RobotHardwareService::DblSequence3](#dblsequence3)|加速度|m/s^2|
|batteries|[OpenHRP::ReferenceForceUpdaterService::BatteryState](型#batterystate)| ||
|voltage|double|電圧値|V|
|current|double|電流値|A|

### interpolationMode

以下の値を列挙。

|名前|説明|
|---|---|
|LINEAR||
|HOFFARBIB||

### STAlgorithm

以下の値を列挙。

|名前|説明|
|---|---|
|TPCC||
|EEFM||
|EEFMQP||
|EEFMQPCOP||
|EEFMQPCOP2||

### ControllerMode

以下の値を列挙。

|名前|説明|
|---|---|
|MODE_IDLE||
|MODE_AIR||
|MODE_ST||
|MODE_SYNC_TO_IDLE||
|MODE_SYNC_TO_AIR||

### EmergencyCheckMode

以下の値を列挙。

|名前|説明|
|---|---|
|NO_CHECK||
|COP||
|CP||
|TILT||

### TwoDimensionVertex

|名前|型|説明|単位|
|---|---|---|---|
|position|[OpenHRP::ReferenceForceUpdaterService::DblArray2](#dblarray2)| |m|

### DblArray2

double型の配列として定義。

### SupportPolygonVertices

|名前|型|説明|単位|
|---|---|---|---|
|position|sequence< [OpenHRP::ReferenceForceUpdaterService::TwoDimensionVertex](#twodimensionvertex) >|||

### IKLimbParameters

|名前|型|説明|単位|
|---|---|---|---|
|ik_optional_weight_vector|sequence< double >|||
|sr_gain|double|||
|avoid_gain|double|||
|reference_gain|double|||
|manipulability_limit|double|||

### stParam

|名前|型|説明|単位|
|---|---|---|---|
|k_tpcc_p|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|k_tpcc_x|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|k_brot_p|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|k_brot_tc|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_k1|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_k2|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_k3|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_zmp_delay_time_const|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_ref_zmp_aux|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_rot_damping_gain|sequence< sequence< double, 3 > >| ||
|eefm_rot_time_const|sequence< sequence< double, 3 > >| ||
|eefm_pos_damping_gain|sequence< sequence< double, 3 > >| ||
|eefm_pos_time_const_support|sequence< sequence< double, 3 > >| ||
|eefm_swing_rot_spring_gain|sequence< sequence< double, 3 > >| ||
|eefm_ee_moment_limit|sequence< sequence< double, 3 > >| ||
|eefm_pos_compensation_limit|sequence< double >| ||
|eefm_rot_compensation_limit|sequence< double >| ||
|eefm_pos_time_const_swing|double| ||
|eefm_pos_transition_time|double| ||
|eefm_pos_margin_time|double| ||
|eefm_leg_inside_margin|double| ||
|eefm_leg_outside_margin|double| ||
|eefm_leg_front_margin|double| ||
|eefm_leg_rear_margin|double| ||
|eefm_body_attitude_control_gain|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_body_attitude_control_time_const|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|eefm_cogvel_cutoff_freq|double| ||
|eefm_wrench_alpha_blending|double| ||
|eefm_pos_margin_time|double| ||
|eefm_alpha_cutoff_freq|double| ||
|eefm_gravitational_acceleration|double| ||
|eefm_ee_pos_error_p_gain|double| ||
|eefm_ee_rot_error_p_gain|double| ||
|eefm_ee_error_cutoff_freq|double| ||
|eefm_ee_rot_error_p_gain|sequence< [OpenHRP::StabilizerService::SupportPolygonVertices](#supportpolygonvertices) >| ||
|eefm_use_force_difference_control|boolean| ||
|eefm_use_swing_damping|boolean| ||
|eefm_swing_damping_force_thre|double| ||
|eefm_swing_damping_moment_thre|double| ||
|eefm_swing_rot_damping_gain|[OpenHRP::StabilizerService::DblArray3](#dblarray3)| ||
|eefm_swing_pos_damping_gain|[OpenHRP::StabilizerService::DblArray3](#dblarray3)| ||
|eefm_ee_forcemoment_distribution_weight|sequence< sequence< double, 6 > >| ||
|st_algorithm|[OpenHRP::StabilizerService::STAlgorithm](#stalgorithm)| ||
|controller_mode|[OpenHRP::StabilizerService::ControllerMode](#controllermode)| ||
|transition_time|double| ||
|is_ik_enable|[OpenHRP::StabilizerService::BoolSequence](#boolsequence)| ||
|is_feedback_control_enable|[OpenHRP::StabilizerService::BoolSequence](#boolsequence)| ||
|is_zmp_calc_enable|[OpenHRP::StabilizerService::BoolSequence](#boolsequence)| ||
|cop_check_margin|double| ||
|cp_check_margin|[OpenHRP::StabilizerService::DblArray4](#dblarray4)| ||
|tilt_margin|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|ref_capture_point|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|act_capture_point|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|contact_decision_threshold|double| ||
|foot_origin_offset|sequence< sequence< double, 3 > >| ||
|emergency_check_mode|[OpenHRP::StabilizerService::EmergencyCheckMode](#emergencycheckmode)| ||
|emergency_check_mode|sequence< [OpenHRP::AutoBalancerService::Footstep](#footstep) >| ||
|is_estop_while_walking|boolean| ||
|emergency_check_mode|sequence< [OpenHRP::StabilizerService::IKLimbParameters](#iklimbparameters) >| ||
|use_limb_stretch_avoidance|boolean| ||
|limb_stretch_avoidance_time_const|double| ||
|limb_stretch_avoidance_vlimit|[OpenHRP::StabilizerService::DblArray2](#dblarray2)| ||
|limb_length_margin|sequence< double >| ||

### BoolSequence

boolean型の配列として定義。

### Command

|名前|型|説明|単位|
|---|---|---|---|
|jointRefs|[OpenHRP::StabilizerService::DblSequence](#dblsequence)| |rad|
|baseTransform|[OpenHRP::StabilizerService::DblSequence](#dblsequence)| ||
|zmp|[OpenHRP::StabilizerService::DblSequence](#dblsequence)| |m|

### tlParam

|名前|型|説明|単位|
|---|---|---|---|
|debug_print_freq|unsigned long| ||
|alarmRatio|double| ||

### torqueControllerParam

|名前|型|説明|単位|
|---|---|---|---|
|tc|double| ||
|ke|double| ||
|kd|double| ||
|ki|double| ||
|alpha|double| ||
|beta|double| ||
