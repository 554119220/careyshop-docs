# 添加一个导航

#### 接口描述：
- 添加一个导航。

#### 请求 URL：
- `http|https://host/api/v1/navigation/method/add.navigation.item/`

#### 请求方式：
- GET
- POST

#### 是否授权：
- 需要授权

#### 业务参数：
|参数名|类型|是否必须|范围值|默认值|示例值|描述|
|:----|:---|:---:|:-----|:-----|:-----|-----|
|name |string |是 |max:100 | |团购 |导航名称 |
|url |string |是 |max:255 | |//careyshop.cn |导航链接 |
|target |string |否 |in:_self,_blank |_self |_blank |打开方式 |
|sort |integer |否 |between:0,255 |50 |50 |导航排序值 |
|status |integer |否 |in:0,1 |1 |1 |导航是否启用 0=禁用 1=启用 |

#### 响应参数：
|参数名|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|status |integer |是 |200 |状态码 |
|message |string |是 |success |消息信息 |
|data |object |是 |[] |返回对象 |

|data|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|name |string |是 |团购 |导航名称 |
|url |string |是 |//careyshop.cn |导航链接 |
|target |string |否 |&#95;blank |打开方式 |
|sort |integer |否 |50 |导航排序值 |
|status |integer |否 |1 |导航是否启用 0=禁用 1=启用 |
|navigation_id |integer |是 |10 |导航编号 |

#### 响应示例：
```json
{
  "status": 200,
  "message": "success",
  "data": {
    "name": "团购",
    "url": "//careyshop.cn",
    "target": "_blank",
    "sort": 50,
    "status": 1,
    "navigation_id": 10
  }
}
```

#### 备注:
无