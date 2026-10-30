# 示例

## 示例 1：引导提问（Agent 应先这样问）

用户：「帮我爬一下校招 JD。」

Agent 应先收集需求，而不是立刻写爬虫，例如：

```text
可以，先确认几项再采集：

1. 公司与校招官网链接？（只要校招不要社招吗？）
2. 届次与性质：只要 2027 正式岗，还是实习也要？
3. 城市优先级？（例如 上海 > 深圳 > 杭州 > 北京）
4. 想要的岗位方向 / 明确不要的方向？
5. 输出 Excel 文件名？要不要「匹配分析」第二张表？
```

确认卡复述后再探测接口。

---

## 示例 2：字节跳动校招+实习合并采集完成说明（原样）

采集已完成，Excel 在项目根目录：`/Users/mac/bytedance-jobs/bytedance_jobs.xlsx`。

**条数**
- 校招：2273
- 实习：5242
- 去重后：**7515**（无重复）

**接口参数（试请求确认）**
- 校招 / 实习都走校园站：`portal_type=2`，`portal_entrance=1`
- 校招：`recruitment_id_list=["201"]`
- 实习：`recruitment_id_list=["202"]`
- CSRF：先打开 `/campus/position`，再 `POST /api/v1/csrf/token`，把 `atsx-csrf-token` 放到 `x-csrf-token`

表头与约定一致：`职位ID` 用页面上的 `code`（如 A34230A），`性质` 为实习/校招，`类型` 有父类时写成「父类-子类」。描述和要求里的换行都保留了，Excel 已开自动换行。

重新跑：

```bash
cd ~/bytedance-jobs
.venv/bin/python fetch_jobs.py --limit 15
```

只验证字段（各频道 2 页）：`.venv/bin/python fetch_jobs.py --verify-only`

## 示例 3：京东 2027 校招筛选采集完成说明（原样）

已完成，文件位于：

`/Users/mac/jd-jobs/jd_2027_campus.xlsx`

结果：
- 总计：62 条，职位 ID 无重复
- JDS 新星计划：42 条
- TET 管理培训生：3 条
- 新锐之星：17 条
- 上海 34、深圳 21、杭州 16、北京 61（多城市岗位重复计数）
- 已排除技术、研发、算法及纯职能岗位
- 六列表头、换行和 Excel 自动换行均验证通过

脚本：`/Users/mac/jd-jobs/fetch_jd_jobs.py`

重新执行：

```bash
cd ~/jd-jobs
.venv/bin/python fetch_jd_jobs.py
```
