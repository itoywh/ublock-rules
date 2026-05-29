# uBlock Rules (EasyList YT + 乘风)

每天自动合并 EasyList YouTube 过滤规则 + [乘风(xinggsf)](https://github.com/xinggsf/Adblock-Plus-Rule) 3 组中文广告过滤规则，生成一条统一的 uBlock Origin 订阅链接。

## 订阅链接

```
https://raw.githubusercontent.com/itoywh/ublock-rules/main/ublock-rules.txt
```

**uBlock Origin 添加方法**：仪表板 → 过滤列表 → 底部「自定义」→ 勾选「导入」→ 粘贴上方链接 → 应用。

## 规则来源

| 来源 | 说明 | 更新频率 |
|------|------|----------|
| **EasyList** (YouTube) | 从 EasyList 完整列表中 grep 提取的 YouTube 专用规则，拦截 YouTube 广告位和元素 | 每日 |
| **乘风 rule.txt** | 百度搜索广告、通用中文网站广告 | 每日 |
| **乘风 mv.txt** | 主流视频平台广告（优酷/爱奇艺/腾讯/B站/斗鱼/虎牙/搜狐/乐视 等） | 每日 |
| **乘风 minority-mv.txt** | 小众视频站广告（低端影视/dmmiku/olevod 等） | 每日 |

## 自动更新

GitHub Actions 每天 UTC 00:00（北京时间 08:00）自动执行：

1. 分别拉取 EasyList 和 3 组乘风规则
2. 合并为单一文件 `ublock-rules.txt`
3. 提交并推送至本仓库

uBlock Origin 会自动检测到文件变更并更新本地规则缓存。

## 手动触发更新

在 [Actions 页面](https://github.com/itoywh/ublock-rules/actions) 点击 "Daily Rule Update" → "Run workflow"。

## 为什么不用社区已有合并源？

- **EasyList 太大**：完整 EasyList 有数万条规则，其中 99% 针对英文网站。本项目仅提取 YouTube 相关规则，不会误杀中文网站。
- **乘风规则独立维护**：3 组规则各有侧重（通用/主流视频/小众视频），保持原始分组结构便于排查误杀。
- **一键订阅**：不用再手动更新、复制粘贴。装好就忘掉。

## 误杀反馈

如果发现某条规则误拦了正常内容，请在 [Issues](https://github.com/itoywh/ublock-rules/issues) 提交反馈，附上被拦截的网址和截图。

## License

本仓库仅为规则聚合脚本，各规则版权归原始作者所有：
- EasyList: [GPLv3](https://easylist.to/)
- 乘风规则: [xinggsf/Adblock-Plus-Rule](https://github.com/xinggsf/Adblock-Plus-Rule)
