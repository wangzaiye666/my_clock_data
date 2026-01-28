# My Clock 节假日数据

此仓库用于托管 [My Clock](https://github.com/wangzaiye666/my_clock_data) 应用的中国法定节假日数据。

## 文件说明

| 文件 | 说明 |
|------|------|
| `holidays.json` | 节假日数据（包含版本号、更新时间和节假日数据） |

## 数据格式

### holidays.json

```json
{
  "version": "v1.0.1",
  "updateTime": "2026-01-04T00:00:00Z",
  "note": "",
  "data": {
    "2024": [
      {
        "date": "2024-01-01",
        "isHoliday": true,
        "name": "元旦"
      },
      {
        "date": "2024-02-04",
        "isHoliday": false,
        "name": "班"
      }
    ],
    "2025": [...],
    "2026": [...]
  }
}
```

**字段说明：**
- `version`: 数据版本号（格式：`年份.序号`，如 `2026.1`、`2027.1`）
- `updateTime`: 数据更新时间（ISO 8601 格式）
- `note`: 临时通知事项，默认为空
- `data`: 按年份组织的节假日数据
  - `date`: 日期（YYYY-MM-DD 格式）
  - `isHoliday`: 是否为法定节假日
  - `name`: 节假日名称，`"班"` 表示调休工作日

## 更新流程

1. 每年 10-12 月国务院发布下一年节假日安排
2. 更新 holidays.js
3. 更新 version.js
4. 提交并推送到 GitHub


## 数据来源

数据根据国务院办公厅发布的节假日安排整理，官方文件可在 [中国政府网](http://www.gov.cn/) 查阅。
其他数据来源API： https://api.apihubs.cn/holiday/get?year=2026&size=366；
            https://github.com/NateScarlet/holiday-cn

## License

MIT license
