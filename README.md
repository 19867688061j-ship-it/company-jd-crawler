# company-jd-crawler

通用技能：引导提问，再写一份可交给任意 AI 或 Agent 执行的招聘 JD 采集指令。

不绑定 Cursor，也不要求对方使用特定工具。

## Author

- **First author / maintainer:** [19867688061j-ship-it](https://github.com/19867688061j-ship-it)（个人项目）
- 本仓库为个人业余作品，**与任何公司无关**，不是公司任务或公司资产。
- License: [MIT](./LICENSE) © 2026 19867688061j-ship-it

## 文件

| 文件 | 作用 |
|------|------|
| `SKILL.md` | 提问顺序、指令框架、字段和筛选判断 |
| `reference.md` | 接口核实与避坑 |
| `examples.md` | 一份完整指令，以及提问示例 |
| `README.md` | 使用说明 |
| `LICENSE` | MIT |

## 怎么用

```bash
git clone https://github.com/19867688061j-ship-it/company-jd-crawler.git
```

支持 Skills 的产品：把整个文件夹放到该产品的 skills 目录。

只支持自定义指令：把 `SKILL.md` 放入系统提示或项目说明。

普通对话：上传或粘贴 `SKILL.md`，并说「按这个技能，先问我，再写采集指令」。

## 默认行为

信息不全时先提问。信息确认后，输出一个可整段复制的 `text` 代码块。只有用户明确要求执行时，才真正采集并生成 Excel。

## Disclaimer

本 Skill 仅指导采集**公开招聘接口**上的岗位信息，供个人求职整理使用。请遵守目标站点服务条款与当地法律；不要用于登录绕过、验证码破解或未授权访问。
