# CF 双语题面 · DeepSeek

[一键安装篡改猴脚本](https://raw.githubusercontent.com/opekefuya64-oss/cf-deepseek-translator/main/cf-deepseek-translator.user.js) · [下载 ZIP 安装包](https://github.com/opekefuya64-oss/cf-deepseek-translator/raw/refs/heads/main/CF-DeepSeek.zip)

给 Chrome 篡改猴使用的 Codeforces 题面翻译脚本。密钥由你在首次使用时填写。脚本不依赖原版 Codeforces Better!，不加载远程脚本，也不会弹出更新提醒。

**安装**：在篡改猴「管理面板 → 实用工具」中找到 ZIP 导入，选择 `CF-DeepSeek.zip`，确认导入并启用脚本。也可以在文本编辑器打开 `cf-deepseek-translator.user.js`，复制全部内容，到篡改猴「添加新脚本」中替换模板并按 Ctrl+S 保存。两种方式选一种即可。

**第一次翻译**：打开或刷新一道 HTML 题目，例如 [4A · Watermelon](https://codeforces.com/problemset/problem/4/A)。在「连接 DeepSeek」窗口粘贴你自己的 DeepSeek API Key，保留默认 Flash 模型，点「保存并翻译」。如篡改猴询问是否允许访问翻译服务，目标应为 `api.deepseek.com`。

**之后使用**：在下一道题面上点「翻译成中文」。每段译文都跟在原文下面；点「隐藏中文」可以只看原文。原题、公式、插图和样例保留，图片里的文字和 PDF 题面不会被翻译。已完成的批次缓存在篡改猴中，缓存命中时不会再次请求 API。

**更换密钥或模型**：点击题面上方「API 设置」，或使用篡改猴菜单里的「CF 双语题面：API 设置」。已保存的密钥不会回显，留空会沿用原密钥。更换模型后，刷新已翻译的页面再翻译。用「清除已保存的密钥」可删除本脚本保存的凭据。

**排查问题**

- 旧脚本还在提示更新：在篡改猴面板中单独停用原版 Codeforces Better!，保留「CF 双语题面 · DeepSeek」，再刷新题目页。
- 看不到「双语题面」：确认当前是题面页，脚本已启用。新版 Chrome 还可在篡改猴的扩展详情页检查「允许用户脚本」。见[篡改猴官方说明](https://www.tampermonkey.net/faq.php?locale=zh&q=Q209)。
- 401 表示密钥被拒绝，402 表示 API 余额不足，429 表示请求太频繁。连接失败时先检查网络和篡改猴对 DeepSeek 域名的访问权限。
- 提示漏译段落或公式：点「重试翻译」。脚本不会显示未通过完整性检查的批次。

**数据去向**：密钥保存于本脚本的篡改猴存储。翻译时通过 HTTPS 直接调用 [DeepSeek 官方接口](https://api-docs.deepseek.com/zh-cn/)。请求含待翻译段落和相关公式，不包含 Codeforces 登录 Cookie、提交代码或样例输入输出。本脚本没有中转服务器。

本脚本独立编写，参考了北极小狐 [OJBetter / Codeforces Better!](https://github.com/beijixiaohu/OJBetter) 的题面翻译交互和公式保护思路，专注于题面翻译。

本仓库使用 [MIT 许可证](LICENSE)。
