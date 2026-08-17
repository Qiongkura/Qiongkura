# 放到你仓库 .github/workflows/metrics.yml（覆盖原文件）
# 更多数据模块（在 compact 模板下仍保持简洁；想要更多可再往下加）
# 注意：模块越多图越大、跑得越慢，且 GitHub API 限流可能让个别区块空白
name: Metrics
on:
  push:
    branches: [main]
  schedule:
    - cron: "0 */6 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          token: ${{ secrets.GITHUB_TOKEN }}
          user: Qiongkura
          template: compact

          # 原有的
          plugin_activity: yes
          plugin_activity_limit: 7
          plugin_languages: yes
          plugin_languages_limit: 10
          plugin_repositories: yes
          plugin_stargazers: yes
          plugin_followup: yes

          # ── 新增模块（每行一组数据）──
          plugin_isocalendar: yes                # 一年的贡献热力日历
          plugin_isocalendar_duration: full-year
          plugin_achievements: yes               # 成就徽章
          plugin_trophies: yes                   # 奖杯墙
          plugin_habits: yes                     # 编码习惯（提交时段/频率）
          plugin_habits_facts: yes
          plugin_habits_charts: yes
          plugin_commits: yes                    # 提交数（按需）
          plugin_commits_limit: 2
          plugin_peoples: yes                    # 一起合作的人（需公开仓库多）
          plugin_peoples_limit: 4
          plugin_discussions: yes                # 讨论（若你开了仓库 Discussions）
          plugin_stars: yes                      # 你 star 过的仓库
          plugin_stars_limit: 4
          plugin_notable: yes                    # 代表仓库
          plugin_topics: yes                     # 热门话题

          # 想更全再加（会明显变大/变慢）：
          # plugin_code: yes                     # 代码片段分析（需要更多 token 权限）
          # plugin_lines: yes                    # 代码行数统计（需要更多 token 权限）
          # plugin_reactions: yes                # 表情反应
          # plugin_calendar: yes, plugin_calendar_limit: 15
          # plugin_fortune: yes                  # 每日一句（纯装饰）
