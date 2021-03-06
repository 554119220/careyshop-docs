# 编辑一篇文章

#### 接口描述：
- 编辑一篇文章。

#### 请求 URL：
- `http|https://host/api/v1/article/method/set.article.item/`

#### 请求方式：
- GET
- POST

#### 是否授权：
- 需要授权

#### 业务参数：
|参数名|类型|是否必须|范围值|默认值|示例值|描述|
|:----|:---|:---:|:-----|:-----|:-----|-----|
|article_id |integer |是 |gt:0 | |22 |文章编号 |
|article_cat_id |integer |否 |gt:0 | |1 |文章分类编号 |
|title |string |否 |max:200 | |标题 |文章标题 |
|image |string |否 |max:255 | |//host/image.jpg |文章封面 |
|content |string |否 | | |正文 |文章内容 |
|source |string |否 |max:60&#124;requireWith:source_url | |网易 |文章来源 |
|source_url |string |否 |max:255&#124;requireWith:source | |www.163.com |来源地址 |
|keywords |string |否 |max:255 | |关键词 |文章关键词 |
|description |string |否 |max:255 | |描述 |文章描述 |
|url |string |否 |max:255 | |http&#58;//163.com |外部连接 |
|target |string |否 |in:&#95;self,&#95;blank |&#95;self |&#95;self |打开方式 |
|is_top |integer |否 |in:0,1 |0 |0 |是否置顶 0=否 1=是 |
|status |integer |否 |in:0,1 |1 |1 |文章状态 0=禁用 1=启用 |

#### 响应参数：
|参数名|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|status |integer |是 |200 |状态码 |
|message |string |是 |success |消息信息 |
|data |object |是 |[] |返回对象 |

|data|类型|是否返回|示例值|描述|
|:-----|:-----|:---:|:-----|-----|
|article_id |integer |是 |22 |文章编号 |
|article_cat_id |integer |否 |1 |文章分类编号 |
|title |string |否 |标题 |文章标题 |
|image |string |否 |//host/image.jpg |文章封面 |
|content |string |否 |正文 |文章内容 |
|source |string |否 |网易 |文章来源 |
|source_url |string |否 |www.163.com |来源地址 |
|keywords |string |否 |关键词 |文章关键词 |
|description |string |否 |描述 |文章描述 |
|url |string |否 |http&#58;//163.com |外部连接 |
|target |string |否 |&#95;self |打开方式 |
|is_top |integer |否 |0 |是否置顶 0=否 1=是 |
|status |integer |否 |1 |文章状态 0=禁用 1=启用 |
|update_time |datetime |是 |2018-05-03 23:57:18 |更新时间 |

#### 响应示例：
```json
{
  "status": 200,
  "message": "success",
  "data": {
    "article_id": 22,
    "article_cat_id": 1,
    "title": "标题",
    "image": "//host/image.jpg",
    "content": "&amp;正文",
    "source": "网易",
    "source_url": "www.163.com",
    "keywords": "关键词",
    "description": "描述",
    "url": "http://163.com",
    "target": "_self",
    "is_top": 0,
    "status": 1,
    "update_time": "2018-05-03 23:57:18"
  }
}
```

#### 备注:
1. 业务参数`是否必须`一栏中被标注为`否`时，可不填写此参数，表示该接口可单独修改某个字段。

2. 当`url`存在值表示跳转到某个地址，`target`表示目标打开方式。