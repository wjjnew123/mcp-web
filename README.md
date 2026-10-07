# mcp-web — MCP Web Runtime（网页读写与浏览器自动化）

面向 AI Agent 的网页读写 + 浏览器自动化 MCP 服务器：**静态极速解析（Axios + Cheerio）** 与 **真实 Chromium 动态渲染** 双内核，共 **20 个工具**。

- 远程端点：`https://mcpweb.wjjnew.cn/mcp`（Streamable HTTP）
- 鉴权：`Authorization: Bearer mcp_sk_xxx`（在 https://mcpweb.wjjnew.cn/ 注册获取，送 500 积分）
- 控制台 / 文档：https://mcpweb.wjjnew.cn/ · https://mcpweb.wjjnew.cn/guide.html

## 客户端配置（远程托管，推荐）

```json
{
  "mcpServers": {
    "mcp-web": {
      "type": "http",
      "url": "https://mcpweb.wjjnew.cn/mcp",
      "headers": { "Authorization": "Bearer <你的 mcp_sk_xxx>" }
    }
  }
}
```

## 工具清单（20）

`fetch_static_web` `fetch_dynamic_web` `fetch_web_auto` `web_observe` `web_extract` `web_extract_table` `web_auto_action` `web_browser` `web_batch` `web_record` `web_screenshot` `web_download` `web_shopify` `web_relay` `browser` `task` `vault` `write_local_html` `read_local_html` `modify_html_dom`

- 读取：静态/动态/自动选择；抽取：Network First、表格结构化。
- 交互：填表/点击/上传下载/跨 iframe/标签页/弹窗/断言/截图/PDF。
- 产物：下载/截图支持内联返回或签名限时链接；本地文件工具作用于私有工作区。

## 本地部署（可选，需自建）

下载 Windows 程序包（登录 https://mcpweb.wjjnew.cn/ 后于首页获取），或使用源码：

```bash
npm install
npm run install:browser   # 安装 Chromium
node src/http-server.js    # HTTP（默认 127.0.0.1:3333/mcp）
```

常用环境变量：`MCP_WEB_HTTP_TOKEN`、`MCP_WEB_ALLOWED_ROOTS`、`MCP_WEB_HEADLESS`、`MCP_WEB_DEPLOY_MODE`。

## 计费

积分制，与其它工具集共用余额；静态读取 ~1、动态读取 ~3、交互按动作数、下载按体积，失败按 20% 计。

## 许可

MIT（见 [LICENSE](./LICENSE)）。使用须遵守目标网站 ToS / robots 与当地法律，严禁爬取未授权网站。
