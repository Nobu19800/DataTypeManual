# IDLファイル
- https://github.com/gbiggs/rtcpcl/blob/master/pc_type/pointcloud.idl

# 目次
- [PointCloud](#pointcloud)


## PointCloud
  
|名前|型|説明|単位|
|---|---|---|---|
|tm|[PointCloudTypes::Time](#time)| ||
|seq|unsigned long| ||
|height|unsigned long| ||
|width|unsigned long| ||
|type|string| ||
|fields|[PointCloudTypes::PointFieldList](#pointfieldlist)| ||
|is_bigendian|boolean| ||
|point_step|unsigned long| ||
|row_step|unsigned long| ||
|data|sequence< octet, 10485760 > or sequence< octet >| ||
|is_dense|boolean| ||


### Time
  
|名前|型|説明|単位|
|---|---|---|---|
|sec|unsigned long|秒|s|
|nsec|unsigned long|ナノ秒|ns|

### DataType
以下の値を列挙。  
  

|名前|説明|
|---|---|
|INT8| |
|UINT8| |
|INT16| |
|UINT16| |
|INT32| |
|UINT32| |
|FLOAT32| |
|FLOAT64| |


### PointField
  
|名前|型|説明|単位|
|---|---|---|---|
|name|string| ||
|offset|unsigned long| ||
|name|[PointCloudTypes::DataType](#datatype)| ||
|count|unsigned long| ||
