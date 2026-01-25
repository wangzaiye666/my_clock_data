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
  "version": "2026.1",
  "updateTime": "2026-01-04T00:00:00Z",
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
- `data`: 按年份组织的节假日数据
  - `date`: 日期（YYYY-MM-DD 格式）
  - `isHoliday`: 是否为法定节假日
  - `name`: 节假日名称，`"班"` 表示调休工作日

## 更新流程

1. 每年 11-12 月国务院发布下一年节假日安排后，更新 `holidays.json`
2. 增加对应年份的数据到 `data` 对象中
3. 更新 `version` 字段（版本号递增，如 `2027.1`）
4. 更新 `updateTime` 字段为当前时间
5. 提交并推送到 GitHub

## Raw 链接

App 通过以下链接获取数据：

- 节假日数据：`https://raw.githubusercontent.com/wangzaiye666/my_clock_data/main/holidays.json`

## 数据来源

数据根据国务院办公厅发布的节假日安排整理，官方文件可在 [中国政府网](http://www.gov.cn/) 查阅。
其他数据来源API： https://api.apihubs.cn/holiday/get?year=2026&size=366；
            https://github.com/NateScarlet/holiday-cn

## License

Apache-2.0 license
