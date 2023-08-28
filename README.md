

<!-- toc -->
- [用户API](#用户api)
  - [1. 用户注册](#1-用户注册)
    - [请求方式](#请求方式)
    - [请求URL](#请求url)
    - [请求参数](#请求参数)
    - [请求体](#请求体)
    - [响应体](#响应体)
    - [错误码](#错误码)
  - [2. 用户更新个人信息API](#2-用户更新个人信息api)
    - [请求方式](#请求方式-1)
    - [请求URL](#请求url-1)
    - [请求参数](#请求参数-1)
    - [请求体](#请求体-1)
    - [响应体](#响应体-1)
    - [错误码](#错误码-1)
  - [3. 获取用户学习汇总情况](#3-获取用户学习汇总情况)
    - [API 方式](#api-方式)
    - [API URL](#api-url)
    - [请求参数](#请求参数-2)
    - [请求体](#请求体-2)
    - [响应体](#响应体-2)
    - [错误码](#错误码-2)
  - [4. 获取用户每日挑战](#4-获取用户每日挑战)
    - [API 方式](#api-方式-1)
    - [API URL](#api-url-1)
    - [请求参数](#请求参数-3)
    - [请求体](#请求体-3)
    - [响应体](#响应体-3)
    - [错误码](#错误码-3)
  - [5. 获取题目列表](#5-获取题目列表)
    - [API 方式](#api-方式-2)
    - [API URL](#api-url-2)
    - [请求参数](#请求参数-4)
    - [请求体](#请求体-4)
    - [响应体](#响应体-4)
  - [6. 更新用户每日挑战](#6-更新用户每日挑战)
    - [API 方式](#api-方式-3)
    - [API URL](#api-url-3)
    - [请求参数](#请求参数-5)
    - [请求体](#请求体-5)
    - [响应体](#响应体-5)
    - [错误码](#错误码-4)
  - [7. 获取每周扩展视频列表](#7-获取每周扩展视频列表)
    - [API 方式](#api-方式-4)
    - [API URL](#api-url-4)
    - [请求参数](#请求参数-6)
    - [请求体](#请求体-6)
    - [响应体](#响应体-6)
    - [错误码](#错误码-5)
  - [8.用户学习视频](#8用户学习视频)
    - [API名称](#api名称)
    - [请求方式](#请求方式-2)
    - [请求URL](#请求url-2)
    - [请求参数](#请求参数-7)
    - [请求体](#请求体-7)
    - [响应体](#响应体-7)
    - [错误码](#错误码-6)
  - [9. 获取最近学习的视频](#9-获取最近学习的视频)
    - [API 方式](#api-方式-5)
    - [API URL](#api-url-5)
    - [请求参数](#请求参数-8)
    - [请求体](#请求体-8)
    - [响应体](#响应体-8)
    - [错误码](#错误码-7)
  - [10. 查询用户个人信息](#10-查询用户个人信息)
    - [请求方式](#请求方式-3)
    - [请求URL](#请求url-3)
    - [请求参数](#请求参数-9)
    - [请求体](#请求体-9)
    - [响应体](#响应体-9)
    - [错误码](#错误码-8)
  - [11.查询用户最近的挑战日期列表](#11查询用户最近的挑战日期列表)
    - [请求方式](#请求方式-4)
    - [请求URL](#请求url-4)
    - [请求参数](#请求参数-10)
    - [请求体](#请求体-10)
    - [响应体](#响应体-10)
    - [错误码](#错误码-9)


# 用户API

## 1. 用户注册

### 请求方式

POST

### 请求URL

```
/api/v1/user/create_user
```

### 请求参数

| 参数名   | 类型   | 是否必选 | 描述                                    |
| -------- | ------ | -------- | --------------------------------------- |
| openid   | string | 是*      | 微信openid,云托管调用则为非必须参数     |
| unionid  | string | 否       | 微信unionid, 接入微信开放平台才会能获取 |
| source   | string | 否       | 微信来源, 云托管调用不用填写            |
| username | string | 否       | 用户昵称                                |
| avatar   | string | 否       | 用户头像URL                             |
| phone    | string | 否       | 手机号码                                |
| email    | string | 否       | 邮箱                                    |
| gender   | int    | 否       | 性别:0未知,1男性,2女性                  |
| ip       | string | 否       | 客户端IP                                |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |

### 错误码

| 错误码 | 错误信息   |
| ------ | ---------- |
| 0      | 创建成功   |
| 1      | 用户已存在 |
| 2      | 创建失败   |

## 2. 用户更新个人信息API

### 请求方式

PUT

### 请求URL

```
/api/v1/user/update_user
```

### 请求参数

| 参数名   | 类型   | 是否必选 | 描述                                    |
| -------- | ------ | -------- | --------------------------------------- |
| openid   | string | 是       | 微信openid,云托管调用则为非必须参数     |
| unionid  | string | 否       | 微信unionid, 接入微信开放平台才会能获取 |
| username | string | 否       | 用户名                                  |
| avatar   | string | 否       | 头像                                    |
| phone    | string | 否       | 手机号码                                |
| email    | string | 否       | 邮箱                                    |
| gender   | int    | 否       | 性别：0未知，1男性，2女性               |
| status   | int    | 否       | 状态：0正常，1禁用, 2注销"              |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |

### 错误码

| 错误码 | 错误信息   |
| ------ | ---------- |
| 0      | 更新成功   |
| 1      | 用户不存在 |
| 2      | 更新失败   |

## 3. 获取用户学习汇总情况

### API 方式

GET

### API URL

```
/api/v1/user/get_learning_summary
```

### 请求参数

| 参数名 | 类型   | 是否必选 | 描述                                |
| ------ | ------ | -------- | ----------------------------------- |
| openid | string | 是*      | 微信openid,云托管调用则为非必须参数 |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |
| data   | json   | 数据     |

```json
{
  "openid": 12345,
  "total_learning_days": 10,
  "total_points": 100,
  "total_videos_watched": 5
}
```

### 错误码

| 错误码 | 错误信息   |
| ------ | ---------- |
| 0      | 更新成功   |
| 1      | 用户不存在 |
| 2      | 更新失败   |

## 4. 获取用户每日挑战

### API 方式

GET

### API URL

```
/api/v1/user/get_daily_challenge
```

### 请求参数

| 参数名     | 类型   | 是否必选 | 描述                                |
| ---------- | ------ | -------- | ----------------------------------- |
| openid     | string | 是       | 微信openid,云托管调用则为非必须参数 |
| challenge_date | string | 否       | 日期: 20230801, 默认则为当天        |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |
| data   | json   | 数据     |

data结构，status:做题情况0表示未做，1表示已做， result:答题结果，0表示错误，1表示正确

```json
{
  "challenge_id": 1,
  "openid": 12345,
  "challenge_date": "20230801",
  "questions": [
    {
      "question_id": 1,
      "status": 1,
      "result": 1
    },
    {
      "question_id": 2,
      "status": 1,
      "result": 0
    },
    {
      "question_id": 3,
      "status": 0,
      "result": null
    },
    {
      "question_id": 4,
      "status": 1,
      "result": 1
    },
    {
      "question_id": 5,
      "status": 1,
      "result": 0
    }
  ],
  "score": 2
}
```

### 错误码

| 错误码 | 错误信息                                 |
| ------ | ---------------------------------------- |
| 0      | 获取成功                                 |
| 1      | 用户不存在                               |
| 2      | 查询日期为历史日期，用户当天并未进行挑战 |

## 5. 获取题目列表

### API 方式

GET

### API URL

```
/api/v1/user/get_questions
```

### 请求参数

| 参数名       | 类型 | 是否必选 | 描述                 |
| ------------ | ---- | -------- | -------------------- |
| question_ids | list | 是       | 获取题目的题目ID列表 |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |
| data   | json   | 题目信息 |

```json
{
  "data": [
    {
      "question_id": 1,
      "content": "下列哪个选项是正确的？",
      "content_image_url": null,
      "option_a": "选项A",
      "option_a_image_url": null,
      "option_b": "选项B",
      "option_b_image_url": null,
      "option_c": "选项C",
      "option_c_image_url": null,
      "option_d": "选项D",
      "option_d_image_url": null,
      "answer": "A",
      "primary_category": "数学",
      "secondary_category": "代数",
      "hint1": "这是提示1",
      "hint1_image_url": null,
      "hint2": "这是提示2",
      "hint2_image_url": null,
      "hint3": "这是提示3",
      "hint3_image_url": null,
      "analysis": "这是解析",
      "summary": "这是总结",
      "source": "来源1",
      "formulas": {
        "formula1": "svg_base64_1",
        "formula2": "svg_base64_21",
      }
    },
    {
      "question_id": 2,
      "content": "下列哪个选项是错误的？",
      "content_image_url": null,
      "option_a": "选项A",
      "option_a_image_url": null,
      "option_b": "选项B",
      "option_b_image_url": null,
      "option_c": "选项C",
      "option_c_image_url": null,
      "option_d": "选项D",
      "option_d_image_url": null,
      "answer": "B",
      "primary_category": "数学",
      "secondary_category": "几何",
      "hint1": "这是提示1",
      "hint1_image_url": null,
      "hint2": "这是提示2",
      "hint2_image_url": null,
      "hint3": "这是提示3",
      "hint3_image_url": null,
      "analysis": "这是解析",
      "summary": "这是总结",
      "source": "来源2"
    }
  ]
}
```

## 6. 更新用户每日挑战

每做完一道题更新一下该题的完成情况
### API 方式

POST

### API URL

```
/api/v1/user/update_daily_challenge
```

### 请求参数

| 参数名         | 类型   | 是否必选 | 描述                                            |
| -------------- | ------ | -------- | ----------------------------------------------- |
| openid         | string | 是       | 微信openid,云托管调用则为非必须参数             |
| challenge_date | string | 否       | 日期: 20230801, 默认则为当天                    |
| question_order | int    | 是       | 挑战中的题目顺序(并非question_id),从1开始, eg:1 |
| status         | int    | 是       | 状态 1已作， 0 未做/跳过                        |
| result         | int    | 是       | 答题结果 1正确 0 错误                           |
| is_complete    | int    | 是       | 完成挑战为1, 未完成0                            |

```json
{
  "question_order": 1,
  "status": 1,
  "result": 1,
  "is_complete": 1,   
}
```


### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |
| data    | json | is_complete=1时有信息 |


特别的，当is_complete=1时，额外返回本次挑战的概况
```json
data = {
  "total_points": summary.total_points,  
  "points": cur_points,
  "correct_num": cur_points
}
```

### 错误码

| 错误码 | 错误信息 |
| ------ | -------- |
| 0      | 提交成功 |
| 1      | 提交失败 |

## 7. 获取每周扩展视频列表

### API 方式

POST

### API URL

```
/api/v1/user/get_weekly_videos
```

### 请求参数

| 参数名     | 类型   | 是否必选 | 描述                                |
| ---------- | ------ | -------- | ----------------------------------- |
| openid     | string | 是       | 微信openid,云托管调用则为非必须参数 |
| start_date | string | 否       | 日期: 20230801, 默认则为本周周一    |
| end_date   | string | 否       | 日期: 20230807, 默认则为本周周日    |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述                                     |
| ------ | ------ | ---------------------------------------- |
| code   | int    | 错误码                                   |
| msg    | string | 错误信息                                 |
| data   | json   | 视频信息, 包括返回的视频数据量和详细信息 |

data: is_watched 字段代表用户历史上是否观看过

```json
{
  "video_num": 2,
  "videos": [
    {
      "video_id": 1,
      "title": "视频1",
      "description": "这是视频1的描述。",
      "video_url": "https://example.com/video1.mp4",
      "thumbnail_url": "https://example.com/video1_thumbnail.jpg",
      "created_date": "20220101",
      "is_watched": 0
    },
    {
      "video_id": 2,
      "title": "视频2",
      "description": "这是视频2的描述。",
      "video_url": "https://example.com/video2.mp4",
      "thumbnail_url": "https://example.com/video2_thumbnail.jpg",
      "created_date": "20220101",
      "is_watched": 1
    }
  ]
}
```

### 错误码

| 错误码 | 错误信息 |
| ------ | -------- |
| 0      | 获取成功 |
| 1      | 获取失败 |

## 8.用户学习视频

### API名称

用户学习视频

### 请求方式

POST

### 请求URL

```
/api/user/update_watched_video
```

### 请求参数

| 参数名       | 类型   | 是否必选 | 描述                                |
| ------------ | ------ | -------- | ----------------------------------- |
| openid       | string | 是       | 微信openid,云托管调用则为非必须参数 |
| video_id     | int    | 是       | 视频ID                              |
| duration     | int    | 是       | 观看时长, 秒                        |
| progress     | float  | 是       | 观看进度, 0-1                       |
| clicked_time | string | 是       | 开始时间，YYYYY-MM-dd HH:mm:ss      |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |

### 错误码

| 错误码 | 错误信息 |
| ------ | -------- |
| 0      | 上报成功 |
| 1      | 上报失败 |

## 9. 获取最近学习的视频

### API 方式

POST

### API URL

```
/api/v1/user/get_learned_videos
```

### 请求参数

| 参数名 | 类型   | 是否必选 | 描述                                |
| ------ | ------ | -------- | ----------------------------------- |
| openid | string | 是*      | 微信openid,云托管调用则为非必须参数 |
| k      | int    | 否       | 最近k个视频                         |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述     |
| ------ | ------ | -------- |
| code   | int    | 错误码   |
| msg    | string | 错误信息 |
| data   | json   | 视频信息 |

data:

```json
{
  "video_num": 2,
  "videos": [
    {
      "video_id": 1,
      "title": "视频1",
      "description": "这是视频1的描述。",
      "video_url": "https://example.com/video1.mp4",
      "thumbnail_url": "https://example.com/video1_thumbnail.jpg",
      "created_date": "20220101"
    },
    {
      "video_id": 2,
      "title": "视频2",
      "description": "这是视频2的描述。",
      "video_url": "https://example.com/video2.mp4",
      "thumbnail_url": "https://example.com/video2_thumbnail.jpg",
      "created_date": "20220101"
    }
  ]
}
```

### 错误码

| 错误码 | 错误信息 |
| ------ | -------- |
| 0      | 获取成功 |
| 1      | 获取失败 |



## 10. 查询用户个人信息

### 请求方式

GET

### 请求URL

```
/api/v1/user/get_user
```

### 请求参数

| 参数名 | 类型   | 是否必选 | 描述                                |
| ------ | ------ | -------- | ----------------------------------- |
| openid | string | 是*      | 微信openid,云托管调用则为非必须参数 |


### 请求体

无

### 响应体

| 参数名 | 类型   | 描述       |
| ------ | ------ | ---------- |
| code   | int    | 错误码     |
| msg    | string | 错误信息   |
| data   | json   | 用户信息｜ |

data 字段
| 参数名   | 类型   | 是否必选 | 描述                                    |
| -------- | ------ | -------- | --------------------------------------- |
| openid   | string | 是*      | 微信openid,云托管调用则为非必须参数     |
| unionid  | string | 否       | 微信unionid, 接入微信开放平台才会能获取 |
| username | string | 否       | 用户名                                  |
| avatar   | string | 否       | 头像                                    |
| phone    | string | 否       | 手机号码                                |
| email    | string | 否       | 邮箱                                    |
| gender   | int    | 否       | 性别：0未知，1男性，2女性               |
| status   | int    | 否       | 状态：0正常，1禁用, 2注销"              |

### 错误码

| 错误码 | 错误信息   |
| ------ | ---------- |
| 0      | 获取成功   |
| 1      | 用户不存在 |
| 2      | 获取失败   |


## 11.查询用户最近的挑战日期列表

### 请求方式

GET

### 请求URL

```
/api/v1/user/get_challenge_dates
```

### 请求参数

| 参数名     | 类型   | 是否必选 | 描述                                |
| ---------- | ------ | -------- | ----------------------------------- |
| openid     | string | 是*      | 微信openid,云托管调用则为非必须参数 |
| start_date | string | 否       | 日期: 20230801, 默认则为本月一日    |
| end_date   | string | 否       | 日期: 20230807, 默认则为本月当日    |

### 请求体

无

### 响应体

| 参数名 | 类型   | 描述       |
| ------ | ------ | ---------- |
| code   | int    | 错误码     |
| msg    | string | 错误信息   |
| data   | json   | 用户信息｜ |

data 字段
| 参数名          | 类型 | 是否必选 | 描述               |
| --------------- | ---- | -------- | ------------------ |
| num_chanllenge  | int  | 否       | 挑战次数           |
| challenge_dates | list | 否       | 参与挑战的日期列表 |

### 错误码

| 错误码 | 错误信息   |
| ------ | ---------- |
| 0      | 获取成功   |
| 1      | 用户不存在 |
| 2      | 获取失败   |