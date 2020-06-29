# 验证广告位置编号是否唯一

#### 接口描述：
- 验证广告位置编号是否唯一。在填写或修改后对其进行检测，避免在提交全部数据后才错误提示。

#### 请求 URL：
- `http|https://host/api/v1/ads_position/method/unique.ads.position.code/`

#### 请求方式：
- GET
- POST

#### 是否授权：
- 需要授权

#### 业务参数：
|参数名|类型|是否必须|范围值|默认值|示例值|描述|
|:----|:---|:---:|:-----|:-----|:-----|-----|
|code |string |是 |max:16 | |index_1 |广告位置编码 |
|exclude_id |integer |否 |gt:0 | |1 |广告排除Id |

#### 响应参数：
|参数名|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|status |integer |是 |200 |状态码 |
|message |string |是 |success |消息信息 |
|data |boolean |是 |true |返回 true 表示可用编码 |

#### 响应示例：
```json
{
    "status": 200,
    "message": "success",
    "data": true
}
```

#### 备注:
无