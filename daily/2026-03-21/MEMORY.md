# 用户记忆 / User Memory

## 用户偏好规则 (CRITICAL - 每次对话启动时必须检查)

### 文件位置
- 全局偏好: `/Users/gh/.claude/user_preferences.md`
- 本地设置: `/Users/gh/.claude/settings.local.json`

### 核心规则
1. **交流语言**: 中文 (Chinese)
2. **代码生成**: 必须添加函数级注释
3. **项目目录**: `/Users/gh/claude_propject/` - 所有新项目必须在此创建
4. **命名规范**: 英文 kebab-case (如 `my-awesome-project`)
5. **重复操作授权**: 无需询问，直接执行
6. **Plan First**: 非平凡任务(3+步骤)先写计划
7. **Autonomous Bug Fixing**: 收到 bug 直接修复
8. **Simplicity First**: 尽可能简单，最小影响
9. **减少询问**: 不要频繁询问用户，能直接执行的直接执行

### 已授权命令 (无需询问)
- `npm install`, `npx bun:*`, `brew install:*`
- `npx skills add *`, `npx prisma *`

## 系统
- OS: macOS (Darwin)
- Shell: zsh
- 主目录: `/Users/gh`
- 工作目录: `/Users/gh/vscode_work`

## 重要习惯
- 每次对话开始时，**必须主动读取并确认** `/Users/gh/.claude/user_preferences.md`
- 不要等用户提醒规则

## Chrome 调试脚本
位置: `~/.claude/scripts/`
| 脚本 | 功能 |
|------|------|
| `chrome-debug-start.sh` | 启动 Chrome 远程调试 (端口 9222) |
| `chrome-debug-stop.sh` | 停止 Chrome 远程调试 |
| `chrome-debug-status.sh` | 查看调试状态 |

使用:
```bash
~/.claude/scripts/chrome-debug-start.sh   # 启动
~/.claude/scripts/chrome-debug-status.sh  # 状态
~/.claude/scripts/chrome-debug-stop.sh    # 停止
```

## Agent Reach & MCP 配置
- **mcporter**: `/usr/local/bin/mcporter` (v0.7.3)
- **Exa 语义搜索**: 已配置 API Key 到 `settings.json` 和 `.zshrc`
- **mcporter 配置**: `/Users/gh/vscode_work/config/mcporter.json`
- **Exa API Key**: `exa_504d7f10-aa31-4856-9ec5-7efa559806b3`

可用渠道 (6/12):
- ✅ GitHub、YouTube、RSS、网页、B站
- ✅ Exa 语义搜索 (已配置 API Key)

命令:
```bash
agent-reach doctor    # 查看状态
mcporter config list  # 列出配置
```

## 个人博客项目
- **GitHub 用户**: gaohui0611
- **博客地址**: https://gaohui0611.github.io
- **项目路径**: `/Users/gh/claude_propject/my-blog`
- **框架**: Hexo + Matery 主题
- **部署**: GitHub Pages + GitHub Actions 自动部署

博客使用:
```bash
cd /Users/gh/claude_propject/my-blog
# 上传 MD 文件到 source/_posts/
git add . && git commit -m "更新" && git push
```

## RedBookSkills 小红书发布
- **技能路径**: `/Users/gh/.agents/skills/redbookskills`
- **详细文档**: `~/.claude/projects/-Users-gh/memory/redbookskills-guide.md`

快速发布:
```bash
cd /Users/gh/.agents/skills/redbookskills

# 准备内容
echo "标题" > /tmp/xhs_title.txt
echo "正文 #标签" > /tmp/xhs_content.txt

# 发布图文
python scripts/publish_pipeline.py --headless \
  --title-file /tmp/xhs_title.txt \
  --content-file /tmp/xhs_content.txt \
  --images "/图片路径.jpg"

# 检查登录
python scripts/cdp_publish.py check-login
```
