# IDLファイル

* [ManipulatorCommonInterface_Common.idl](http://svn.openrtm.org/OpenRTM-aist/trunk/OpenRTM-aist/src/lib/rtm/ext/ManipulatorCommonInterface_Common.idl)
* [ManipulatorCommonInterface_DataTypes.idl](http://svn.openrtm.org/OpenRTM-aist/trunk/OpenRTM-aist/src/lib/rtm/ext/ManipulatorCommonInterface_DataTypes.idl)
* [ManipulatorCommonInterface_Middle.idl](http://svn.openrtm.org/OpenRTM-aist/trunk/OpenRTM-aist/src/lib/rtm/ext/ManipulatorCommonInterface_Middle.idl)

# 目次

* [TimedJointPos](#timedjointpos)

## TimedJointPos

ジョイントの位置を通信するためのデータ型。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|pos|[JARA_ARM::JointPos](#jointpos)|ジョイントの位置|m or rad|

### JointPos

double型の配列。
ジョイントの位置を表現。

## LimitValue

ジョイントの可動範囲を表現。

|名前|型|説明|単位|
|---|---|---|---|
|upper|double|現在の位置|m or rad|
|lower|double|現在の速度|m or rad|

## RETURN_ID

デバイスの状態を表現。

|名前|型|説明|単位|
|---|---|---|---|
|id|long|||
|comment|string|||

|名前|値|説明|
|---|---|---|
|OK|0|正常|
|NG|-1|以上|
|STATUS_ERR|2||
|VALUE_ERR|3||
|NOT_SV_ON_ERR|4||
|FULL_MOTION_QUEUE_ERR|5||
|NOT_IMPLEMENTED|6|定義なし|

## Alarm

アラームを表現。

|名前|型|説明|単位|
|---|---|---|---|
|code|unsigned long|||
|type|[JARA_ARM::AlarmType](#alarmtype)|||
|description|string|||

### AlarmType

以下の値を列挙。

|名前|説明|
|---|---|
|FAULT||
|WARNING||
|UNKNOWN||

## ULONG

unsigned long型。

### ManipInfo

|名前|型|説明|単位|
|---|---|---|---|
|manufactur|string|||
|type|string|||
|axisNum|[JARA_ARM::ULONG](#ulong)|||
|cmdCycle|[JARA_ARM::ULONG](#ulong)|||
|isGripper|boolean|||

## CarPosWithElbow

|名前|型|説明|単位|
|---|---|---|---|
|axisNum|[JARA_ARM::HgMatrix](#hgmatrix)|||
|elbow|double|||
|structFlag|[JARA_ARM::ULONG](#ulong)|||

### HgMatrix

double型の[3][4]の配列。

## CartesianSpeed

|名前|型|説明|単位|
|---|---|---|---|
|translation|double|||
|rotation|double|||
