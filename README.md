# company-jd-crawler

通用「公司校招 / 招聘 JD 采集」Skill：引导式提问 → 公开 API 探测 → 验证 → 筛选 → Excel。

**不绑定 Cursor。** 任何能加载 Markdown 指令 / Agent Skill 的工具都可以用。

## Author

- **First author / maintainer:** [19867688061j-ship-it](https://github.com/19867688061j-ship-it)（个人项目）
- 本仓库为个人业余作品，**与任何公司无关**，不是公司任务或公司资产。
- License: [MIT](./LICENSE) © 2026 19867688061j-ship-it

## 目录

| 文件 | 作用 |
|------|------|
| `SKILL.md` | 主流程（提问清单、采集步骤、Excel 模板） |
| `reference.md` | 接口判断标准与避坑 |
| `examples.md` | 提问示例与完成输出示例 |
| `README.md` | 本说明 |
| `LICENSE` | MIT |

## 在不同环境怎么用

### 方式 A：当作 Agent Skill（推荐）

把整个 `company-jd-crawler` 文件夹复制到该产品的 skills 目录，并确保会读取其中的 `SKILL.md`。

常见做法：

- **Cursor**：复制到 `~/.cursor/skills/company-jd-crawler/`
- **Claude / 其他支持 Skills 的客户端**：按该产品文档放到 skills 目录，或在项目里引用
- **仅支持自定义指令**：把 `SKILL.md` 正文（可连同 reference 要点）粘贴进 Custom Instructions / System Prompt

### 方式 B：对话里手动唤起

开聊时说：

```text
请严格按 company-jd-crawler 这个 skill 执行：先引导式提问，确认需求后再爬公开接口导出 Excel。
```

并把本文件夹路径发给 Agent，或把 `SKILL.md` 贴进对话。

### 方式 C：发给朋友

压缩整个文件夹发送即可；对方解压后用方式 A 或 B。

```bash
git clone https://github.com/19867688061j-ship-it/company-jd-crawler.git
```

## Disclaimer

本 Skill 仅指导采集**公开招聘接口**上的岗位信息，供个人求职整理使用。请遵守目标站点服务条款与当地法律；不要用于登录绕过、验证码破解或未授权访问。
