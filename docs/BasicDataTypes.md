# IDLファイル

* [BasicDataType.idl](http://svn.openrtm.org/OpenRTM-aist/trunk/OpenRTM-aist/src/lib/rtm/idl/BasicDataType.idl)

# 目次

* [Time](#time)
* [TimedState](#timedstate)
* [TimedShort](#timedshort)
* [TimedLong](#timedLong)
* [TimedUShort](#timedushort)
* [TimedULong](#timedulong)
* [TimedFloat](#timedfloat)
* [TimedDouble](#timeddouble)
* [TimedWChar](#timedwchar)
* [TimedBoolean](#timedboolean)
* [TimedString](#timedstring)
* [TimedWString](#timedwstring)
* [TimedLongSeq](#timedlongseq)
* [TimedUShortSeq](#timedushortseq)
* [TimedULongSeq](#timedulongseq)
* [TimedFloatSeq](#timedfloatseq)
* [TimedDoubleSeq](#timeddoubleseq)
* [TimedCharSeq](#timedcharseq)
* [TimedWCharSeq](#timedecharseq)
* [TimedBooleanSeq](#timedbooleanseq)
* [TimedOctetSeq](#timedoctetseq)
* [TimedStringSeq](#timedstringseq)
* [TimedWStringSeq](#timedwstringseq)

## Time

時間を格納する。
主に他のデータ型のタイムスタンプで使用する。

|名前|型|説明|単位|
|---|---|---|---|
|sec|unsigned long|秒|s|
|nsec|unsigned long|ナノ秒(1E-9秒)|ns|

## TimedState

見ての通りTimedShort型と名前が同じで中身が違うだけなので使わない方がいい。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|short|状態||

## TimedShort

short型のデータを通信する。
値の範囲は`-32768 < data < 32768`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|short|データ||

## TimedLong

long型のデータを通信する。
値の範囲は`-2147483648 < data < 2147483648`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|long|データ||

## TimedUShort

unsigned short型のデータを通信する。
値の範囲は`0 < data < 65534`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|unsigned short|データ||

## TimedULong

unsigned long型のデータを通信する。
値の範囲は`0 <= d < 4294967296`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|unsigned long|データ||

## TimedFloat

float型のデータを通信する。
値の範囲は`-3.4E+38 < data < 3.4E+38`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|float|データ||

## TimedDouble

float型のデータを通信する。
値の範囲は`-1.7E+308 < d < 1.7E+308`。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|double|データ||

## TimedChar

char型のデータを通信する。
使わない方がいい。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|char|データ||

## TimedWChar

wchar型のデータを通信する。
使う機会はない。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|wchar|データ||

## TimedBoolean

boolean型のデータを通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|boolean|データ||

## TimedOctet

octet型のデータを通信する。
使う機会はない。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|octet|データ||

## TimedString

文字列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|string|データ||

## TimedWString

ワイド文字列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|wstring|データ||

## TimedShortSeq

short型配列を通信する。
整数値のデータならなんでもこれに入れればいいと言うわけではないので注意。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< short >|データ||

## TimedLongSeq

long型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< unsigned short >|データ||

## TimedUShortSeq

unsigned short型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< unsigned short >|データ||

## TimedULongSeq

unsigned long型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< unsigned long >|データ||

## TimedFloatSeq

float型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< float >|データ||

## TimedDoubleSeq

double型配列を通信する。
モーターの角度を入力する際によく使用されるが、TimedJointPos型やActArrayState型を使うのが推奨されている。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< double >|データ||

## TimedCharSeq

char型配列を通信する。
使わない方がいい。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< char >|データ||

## TimedWCharSeq

wchar型配列を通信する。
使わない方がいい。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< wchar >|データ||

## TimedBooleanSeq

boolean型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< boolean >|データ||

## TimedOctetSeq

octet型配列を通信する。
バイト列の通信を行うので、かつては画像データのやり取りに使われていた。
音データでは共通化が進んでいないため未だに使われている。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< octet >|データ||

## TimedStringSeq

string型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< string >|データ||

## TimedWStringSeq

wstring型配列を通信する。

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](#time)|タイムスタンプ||
|data|sequence< wstring >|データ||
