# 编辑一个商品属性主体

#### 接口描述：
- 编辑一个商品属性主体。

#### 请求 URL：
- `http|https://host/api/v1/goods_attribute/method/set.goods.attribute.body.item/`

#### 请求方式：
- GET
- POST

#### 是否授权：
- 需要授权

#### 业务参数：
|参数名|类型|是否必须|范围值|默认值|示例值|描述|
|:----|:---|:---:|:-----|:-----|:-----|-----|
|goods_attribute_id |integer |是 |gt:0 | |3 |商品属性编号 |
|attr_name |string |否 |max:60 | |内存 |商品属性名称 |
|description |string |否 |max:255 | |描述 |商品属性描述 |
|icon |string |否 |max:64 | |//pc.png |商品属性图标(图片) |
|goods_type_id |integer |否 |gt:0 | |2 |所属商品模型编号 |
|sort |integer |否 |between:0,255 | |50 |商品属性排序值 |

#### 响应参数：
|参数名|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|status |integer |是 |200 |状态码 |
|message |string |是 |success |消息信息 |
|data |object |是 |[] |返回对象 |

|data|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|goods_attribute_id |integer |是 |3 |商品属性编号 |
|attr_name |string |否 |内存 |商品属性名称 |
|description |string |否 |描述 |商品属性描述 |
|icon |string |否 |//pc.png |商品属性图标(图片) |
|goods_type_id |integer |否 |2 |所属商品模型编号 |
|sort |integer |否 |50 |商品属性排序值 |

#### 响应示例：
```json
{
  "status": 200,
  "message": "success",
  "data": {
    "goods_attribute_id": 4,
    "attr_name": "内存",
    "description": "描述",
    "icon": "//pc.png",
    "goods_type_id": 2,
    "sort": 50
  }
}
```

#### 备注:
1. 业务参数`是否必须`一栏中被标注为`否`时，可不填写此参数，表示该接口可单独修改某个字段。