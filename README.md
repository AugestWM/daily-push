# 每日推送

每日金价、新闻推送至微信

## 配置

在 GitHub 仓库设置中添加 Secrets：

1. 进入仓库 → Settings → Secrets and variables → Actions
2. 添加以下 Secrets：

| Name | 说明 |
|------|------|
| `GOLD_API_KEY` | 小小API密钥（仅新闻需要） |
| `WECHAT_APPID` | 公众号AppID |
| `WECHAT_SECRET` | 公众号AppSecret |
| `WECHAT_TEMPLATE_ID` | 消息模板ID |
| `WECHAT_OPENID` | 接收者微信号（需加入白名单） |

## 获取模板ID

1. 微信公众平台测试号后台 → 测试号管理
2. 新增测试模板：
   - 标题：`每日简报`
   - 内容：
   ```
   {{first.DATA}}
   金价：{{keyword1.DATA}}
   新闻：{{keyword2.DATA}}
   {{remark.DATA}}
   ```

## 触发

- 每日 9:00 自动执行
- 也可手动触发（Workflow dispatch）
