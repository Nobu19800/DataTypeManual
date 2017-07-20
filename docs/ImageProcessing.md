# IDLファイル
- http://svn.openrtm.org/OpenRTM-aist/trunk/OpenRTM-aist/src/lib/rtm/ext/CameraCommonInterface.idl

# 目次
- [TimedCameraImage](#timedcameraimage)
- [TimedMultiCameraImage](#timedmulticameraimage)



## TimedCameraImage
画像データを表現するデータ型。  

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|[Img::CameraImage](#cameraimage)|データ||
|error_code|long|エラー情報||


### CameraImage
画像情報を格納する。  

|名前|型|説明|単位|
|---|---|---|---|
|captured_time|[RTC::Time](基本データ型#time)|撮影時刻||
|image|[Img::ImageData](#imagedata)|画像データ||
|intrinsic|[Img::CameraIntrinsicParameter](#CameraIntrinsicParameter)|カメラ内部パラメータ||
|extrinsic|[Img::Mat44](#mat44)|カメラ外部パラメータ||


### CameraIntrinsicParameter
カメラの内部パラメータ。  

|名前|型|説明|単位|
|---|---|---|---|
|matrix_element|double[5]|カメラパラメータ||
|distortion_coefficient|sequence< double >|カメラの歪みラメータ||


### ImageData
画像の生データを格納。  

|名前|型|説明|単位|
|---|---|---|---|
|width|long|画像の幅|pixel|
|height|long|画像の高さ|pixel|
|format|[Img::ColorFormat](#colorformat)|色フォーマット||
|raw_data|sequence< octet >|生データ||


### ColorFormat
以下の値を列挙。  
色フォーマットを表現。  

|名前|説明|
|---|---|
|CF_UNKNOWN|不明|
|CF_RGB|RGBカラー|
|CF_GRAY|グレースケール|
|CF_JPEG|JPEG圧縮|
|CF_PNG|PNG圧縮|
|RGB|RGB|
|RLE8|ランレングス圧縮|
|RLE|ランレングス圧縮|
|RAW|未加工|
|RGBA|RGBAカラー|
|AYUV||
|CLJR||
|CYUV||
|GREY||
|IRAW||
|IUYV||
|IY41||
|IYU1||
|IYU2||
|HDYC||
|UYNV||
|UYVP||
|V210||
|V422||
|V655||
|VYUV||
|YUNV||
|YVYU||
|Y41P||
|Y211||
|Y41T||
|Y42T||
|YUVP||
|Y800||
|Y8||
|Y16||


## TimedMultiCameraImage
複数のカメラの画像情報を格納するデータ型。  

|名前|型|説明|単位|
|---|---|---|---|
|tm|[RTC::Time](基本データ型#time)|タイムスタンプ||
|data|[Img::MultiCameraImage](#multicameraimage)|データ||
|error_code|long|エラー情報||


### MultiCameraImage
複数の画像の情報を格納。  

|名前|型|説明|単位|
|---|---|---|---|
|image_seq|sequence< [Img::CameraImage](#cameraimage) >|画像情報||
|camera_set_id|long|カメラセットのID||



### NamedValue
名前付きの値を格納。  

|名前|型|説明|単位|
|---|---|---|---|
|name|string|名前||
|value|string|値||

### NVList
[Img::NamedValue](#namedvalue)型の配列として定義。  



### CameraDeviceProfile
カメラのデバイス情報を格納。

|名前|型|説明|単位|
|---|---|---|---|
|devtypeid|string|||
|guid|string|||
|unit|short|||
|vendor_name|string|開発元の名前||
|model_name|string|製品名||
|intrinsic|[Img::CameraIntrinsicParameter](#cameraintrinsicparameter)|カメラの内部パラメータ||
|properties|[Img::NVList](#nvlist)|その他の情報||

