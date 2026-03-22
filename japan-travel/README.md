# 日本私藏旅行手帖 · 部署指南

## 文件说明

```
japan-travel/
├── index.html      ← 主页面
├── api/
│   └── chat.js     ← 后端接口（转发 Claude API 请求）
├── vercel.json     ← Vercel 配置
└── README.md
```

---

## 部署步骤（约 15 分钟）

### 第一步：上传到 GitHub

1. 打开 https://github.com，登录或注册账号
2. 点击右上角 **+** → **New repository**
3. 仓库名填 `japan-travel`，选 **Public**，点击 **Create repository**
4. 进入仓库页面，点击 **uploading an existing file**
5. 把以下三个文件/文件夹全部拖入上传：
   - `index.html`
   - `api/chat.js`（注意保持 api 文件夹结构）
   - `vercel.json`
6. 点击 **Commit changes**

### 第二步：在 Vercel 部署

1. 打开 https://vercel.com，用 GitHub 账号登录
2. 点击 **Add New Project**
3. 找到刚才创建的 `japan-travel` 仓库，点击 **Import**
4. 框架选 **Other**，其他默认，点击 **Deploy**
5. 等待约 1 分钟，部署完成

### 第三步：添加 API Key（重要！）

1. 打开 https://console.anthropic.com，登录后点击 **API Keys**
2. 点击 **Create Key**，复制生成的 Key（以 `sk-ant-` 开头）
3. 回到 Vercel，进入你的项目 → **Settings** → **Environment Variables**
4. 添加一个变量：
   - **Name**：`ANTHROPIC_API_KEY`
   - **Value**：粘贴你的 API Key
   - 点击 **Save**
5. 回到项目首页，点击 **Redeploy** 让配置生效

### 第四步：获取网址

部署完成后，Vercel 会给你一个永久网址，格式如：
```
https://japan-travel-xxx.vercel.app
```

复制这个网址，发给朋友即可访问！

---

## 注意事项

- API Key 存在 Vercel 服务器端，朋友看不到，安全
- Anthropic 按使用量收费，地点信息加载会消耗少量 Token
- 如果访问量很小（朋友偶尔看看），费用基本可以忽略不计
