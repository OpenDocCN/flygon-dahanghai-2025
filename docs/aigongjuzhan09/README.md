# AI 工具站丨实战手册丨 2025 年 9 月航海

> 来源：[https://ocn93f5d9olj.feishu.cn/docx/RxssdslSfo1u9QxSttucaKYanwh](https://ocn93f5d9olj.feishu.cn/docx/RxssdslSfo1u9QxSttucaKYanwh)

1.  基础环境与账号准备

# 1\. 本章概要

# 💡

本章概要：

本章主要介绍如何从零开始搭建一个完整的开发与部署环境，为后续的编程实战做好准备。

实战步骤：

准备云端服务与账号：

Github：用于代码托管与版本控制。

Google：用于关联登录各类开发平台。

Vercel：用于项目的前端或全栈部署。

Supabase：提供后端数据库及认证服务。

安装本地开发工具：

Node.js：提供 JavaScript 运行环境。

pnpm：高效的包管理工具。

Git：用于代码版本管理。

Trae/VS Code：代码编辑器。

Postman：用于 API 接口测试。

完整开发环境为之后的项目开发奠定基础，一次配置终身受益。

# 💡

# 本章航线图

完成本章节的学习和实操，即可完成航线图的：

第一阶段：启航准备（约 3 天）

1.  商业模式与前景：理解 AI+工具站的商业模式与市场机遇（约 1 天）

1.  环境配置：准备Vscode、Github、Vercel 等基础开发环境（约 2 天）

# 2\. Google 账号

作用：用于绑定各类第三方工具和云服务，方便账号管理和跨平台登录。

建议用途：

登录 Vercel、Supabase 等平台。

使用 Google Drive 或 Google Docs 存储开发文档。

Google 账号注册请看下面这个视频：

如何注册google账号.mp4【在线播放】

# 3\. Github 账号

作用：托管代码仓库、管理版本、支持 CI/CD（持续集成/持续部署）自动化。

注册地址：https://github.com

账号注册请观看以下视频：

Github 注册.mp4【在线播放】

# 4\. Vercel 账号

作用：全球领先的前端和全栈项目部署平台，完美支持 Next.js、React 等应用。

操作步骤：

访问注册地址：https://vercel.com

强烈建议使用 Github 账号直接登录，这样可以无缝衔接，实现代码提交后自动部署。

Vercel 账号注册请观看以下视频：

Vercel注册.mp4【在线播放】

# 5\. Supabase 账号

作用：一个开源的 Firebase 替代品，提供云端数据库（PostgreSQL）、用户认证、文件存储和实时数据管理等后端服务。

注册地址：https://supabase.com/

1.  开发环境配置与工具安装

在开始写代码之前，我们需要先把“兵器”准备好。别担心，我会一步步带你完成所有配置，确保你的开发环境万无一失。为此，我专门录制了视频，并标注了时间戳，方便你随时查阅。

开发环境配置&工具安装.mp4【在线播放】

00:00-02:00 开发环境配置与工具简介

02:00-08:16 安装 Node.js

08:16-10:56 安装 npm、pnpm

10:56-13:10 安装 Git

13:10-17:32 安装 Trae

17:32-20:22 安装 Postman

ps：Trae 登录需要 google 账号

视频内容补充：

如果在 09:13 安装 npm 时，PowerShell 提示执行策略限制的错误（如下图）：

![](img/bd77f9d9b7b77f326b441c9ad88de5ea.png)

请在 PowerShell 中输入以下命令并回车，即可解决：

```
Set-ExecutionPolicy -Scope CurrentUser -ExecutionPolicy RemoteSigned -Force
```

![](img/87c523b12686e14ae5fcb0116ca6383e.png)

1.  必备工具清单

开始之前，我们先过一遍需要安装的工具：

Node.js: JavaScript 运行环境，后端开发的基础。

pnpm: 更快、更节省空间的包管理工具。

Git: 代码版本控制工具，团队协作必备。

Trae/VS Code: 代码编辑器，我们写代码的地方。

Postman: API 测试工具，调试后端接口的利器。

# 2\. 详细安装步骤

# 2.1 安装 Node.js（JavaScript 运行环境）

什么是 Node.js？

简单来说，Node.js 让 JavaScript 这门原本只能在浏览器里运行的语言，也能在你的电脑（服务器）上运行。它是我们后续所有开发工作的基础。

安装步骤：

1\. 打开 Node.js 官网

1.  网站会自动识别你的操作系统，显示对应的安装命令

1.  复制安装命令

1.  打开终端（Mac 用户）或 PowerShell（Windows 用户）

Mac: 按 Command + 空格，搜索"终端"

Windows: 按 Win + R，输入"PowerShell"

1.  粘贴命令并按回车执行

![](img/7f59e42117598934bfcf85d7a83e59c8.png)

Mac 就 打开终端 Shell Windows 打开 Powershell ， 把复制的命令粘贴在终端执行

![](img/9f3429a31eebef743f674c74b4500869.png)

安装完成之后 我们可以查看 node 版本， 有显示说明安装成功

```
splendor@splendordeMac-mini ~ % node -v
v20.10.0
```

说明：安装 Node 会自动安装 npm 不需要单独安装（windows 版本安装会遇到问题，看视频解决）

![](img/5eac72d2b53bebc14f68e2544e0f621d.png)

![](img/1d7f442bf125a823207018e70dd9c6a0.png)

# 2.2 安装 pnpm（高效的包管理工具）

什么是 pnpm？

pnpm 是一个 JavaScript 包管理工具，和 npm、yarn 类似，但它更快、更节省磁盘空间。因为依赖包会复用，安装速度通常比 npm 和 yarn 更快，现在非常流行。

安装步骤：

因为前面已经安装了 npm，就可以通通过 npm 直接安装 pnpm

```
npm install -g pnpm
```

验证安装：

安装完成后，运行命令测试是否安装成功：

```
pnpm -v
```

![](img/d60b8ba05966d8b408f55135e3ed294f.png)

# 2.3 安装 Git（代码版本管理）

什么是 Git？

Git 就像是代码的“后悔药”和“时光机”。它能帮你管理代码的每一个版本，让你随时可以回到之前的状态，也是团队协作开发的基础。

安装步骤：

1\. 访问 Git 官网

1.  下载适合你系统的安装包

1.  双击安装，一路点击"下一步"即可

验证安装：

在终端输入以下命令：

```
git --version
```

如果显示类似下面的信息，就说明安装成功了。

```
git version 2.39.5
```

# 2.4 安装代码编辑器

你可以选择以下任一编辑器：

选项 A：Trae（AI 增强版编辑器）

1\. 访问 Trae 官网

1.  下载国际版并安装

1.  它内置了 AI 编程助手，类似于 Cursor，非常强大。如果你已经习惯了 VS Code，也可以通过插件形式使用。

官网下载安装程序 https://www.trae.ai/ 这里我们使用国际版，如果选择购买会员可以用 Calude 等比较好用的模型，里面也有 Deepseek 等免费模型。

![](img/49b436ea60269ca1951f8b7bdf53e6ca.png)

选项 B：VS Code + AI 插件

1\. 下载 VS Code

1.  安装后可添加 AI 插件如 Claude Code

推荐插件：

Prettier: 自动格式化代码，让你的代码永远保持整洁。

ESLint: 检查代码规范，帮你写出更健壮的代码。

GitLens: 增强 Git 功能，让你能清晰地看到每一行代码的修改历史。

![](img/8a1846629d6f17146060ce02af060916.png)

# 2.5\. 安装 Postman（API 测试工具）

什么是 Postman？

Postman 是一个专门用来测试网络接口（API）的工具。在后端开发中，你可以用它来模拟前端请求，验证接口是否正常工作，是前后端联调的必备神器。

使用场景：

接口调试：开发 API 时，先用 Postman 测试请求是否能返回正确的数据。

前后端联调：当前端还没写好页面时，可以用 Postman 先模拟请求，看后端接口数据对不对。

自动化测试：编写测试脚本，自动验证接口的稳定性。

接口文档管理：生成 API 文档，方便团队共享。

安装步骤：

.

访问 Postman 官网下载页面。

.

下载对应你操作系统的版本并安装。

![](img/4e824de3f582ddff34d21fca935407bf.png)

![](img/8adbc298f4c9f40483abe46597007726.png)

1.  热身 1：5 分钟生成第一个 AI 小游戏

# 1\. 本章概要

本章概要：

本章将通过两个热身项目的实战，让你对 AI 工具站的开发流程有个初步认知，亲身感受 AI 开发的强大和工具的价值。

项目 1 (小试牛刀)：我们将用配置好的开发环境，借助 AI 编程，在 5 分钟内生成一个经典的“贪吃蛇”游戏，并完成自动化部署，让你的朋友都能玩上你做的游戏网站。

项目 2 (进阶挑战)：这个项目会更复杂一些，我们将完整地走一遍 需求分析 -> 产品设计 -> 编码实现 -> 项目部署上线 的标准流程，开发一个视频下载工具站。

实战步骤：

项目 1：5 分钟生成 AI 小游戏

使用 AI 编程，生成项目代码。

将代码提交到 GitHub。

自动化部署并分享你的网站。

项目 2：2 小时开发视频下载工具站

需求分析与产品设计。

技术方案设计。

编码实现。

项目部署上线。

# 本章航线图

完成本章节的学习和实操，即可完成航线图的：

第二阶段：实战初体验 (约 5 天)

1.  AI 小游戏项目：在 5 分钟内生成并部署第一个 AI 小游戏（约 2 天）。

1.  视频下载工具：开发视频下载工具站，完成需求分析与实现（约 3 天）。

5分钟用AI生成一个游戏网站.mp4【在线播放】

00:00-03:36 使用 AI 生成项目代码

03:36-08:28 提交代码到 GitHub 仓库

08:28-09:22 自动化部署与分享

1.  使用 AI 生成项目代码

步骤一：打开 Trae 编辑器，并创建一个新的项目目录。

步骤二：在 Trae 的 AI 对话框中，输入你的需求，比如：

“帮我生成一个贪吃蛇游戏网站”

步骤三：在代码生成过程中，如果 AI 需要你确认或执行某些操作，请按照提示手动执行。

![](img/554b8ae0b52ca55778fec02f20abd180.png)

步骤四：确认执行后，Trae 会自动启动一个 Web 服务，并为你预览游戏界面。

步骤五：持续优化需求。 比如，我觉得游戏速度太快了，可以继续对 AI 说：

“加上速度控制，太快了，让用户可以自己控制移动速度”

步骤六：等待代码生成完毕后，刷新预览界面，你就会看到新增的速度控制功能。

# 3\. 提交代码到 GitHub 仓库

# 3.1 在 GitHub 创建代码仓库

步骤一：登录 GitHub，点击右上角的 “+” 号，选择 “New repository”。

![](img/d4824fbc31a3a11591711da046f7a54b.png)

![](img/c49f27d58423589b14f2f5b23c78e3bd.png)

步骤二：填写仓库名称（例如 SnakeGame），并确保仓库是 Public（公开） 的。

注意：必须设置为公开，因为我们后面要用免费的 GitHub Pages 功能来部署网站。

步骤三：点击 “Create repository” 完成创建。

![](img/5b3cb6a3a20e6389e55dc717046f5d6d.png)

注意不要设置为私有项目，因为后面需要用到 Github Pages 部署

# 3.2 配置 SSH 免密登录

为了让你的电脑能安全地和 GitHub 通信，我们配置一下 SSH 密钥，这样以后提交代码就不用反复输入密码了。

![](img/80902fae8571cbc6b7621a90b3c8e33d.png)

步骤一：生成 SSH 密钥

打开终端（Terminal 或 PowerShell），输入以下命令（记得把邮箱换成你自己的）

```
ssh-keygen -t rsa -b 4096 -C "你的邮箱@example.com"
```

解释一下参数：

-t rsa：指定密钥类型为 RSA。

-b 4096：指定密钥长度为 4096 位（更安全）。

-C "你的邮箱@example.com"：为密钥加上备注，一般用邮箱。

执行后，系统会提示你保存路径和输入密码，直接一路回车即可。

步骤二：查看并复制公钥

在终端输入以下命令，查看并复制生成的公钥内容：

然后我们复制公钥内容到 github

```
cat ~/.ssh/id_rsa.pub
```

步骤三：添加到 GitHub

登录 GitHub，进入 Settings -> SSH and GPG keys。

点击 “New SSH key”。

将刚刚复制的公钥内容粘贴进去，保存即可。

![](img/0e41bbc93ebf05693759500907682428.png)

# 3.3 本地仓库初始化与代码推送

# 3.3.1 初始化 Git 仓库并提交代码

步骤一：回到 Trae 编辑器，在终端中执行 git init 命令，初始化本地 Git 仓库。

步骤二：将所有文件添加到暂存区。

步骤三：提交代码（Commit）。你可以自己写提交信息，也可以点击旁边的 AI 按钮，让 AI 帮你生成一条详细的提交记录。

# 3.3.2 添加远程仓库地址并推送

步骤一：回到 GitHub 仓库页面，复制 SSH 格式的仓库地址。

![](img/d306ac90351a3f1a3d58447a3bf17131.png)

步骤二：在 Trae 的终端中，执行以下命令，将本地仓库与远程仓库关联起来（记得把地址换成你自己的）：

```
 git remote add origin git@github.com:fuyunzhishang/SnakeGame.git
```

步骤三：点击 Trae 编辑器左侧的 发布（Publish Branch） 按钮，将本地代码推送到 GitHub。

![](img/ca4fd4673dc7d179612495a8f11d5417.png)

步骤四：刷新你的 GitHub 仓库页面，就能看到刚刚推送的代码了。

![](img/c323455b6fc391cbef3eeedc65bb33de.png)

# 4\. 自动化部署与分享

# 4.1 使用 GitHub Pages 部署网站

现在，我们来把这个游戏网站发布到互联网上。

步骤一：进入你 GitHub 上的项目仓库，点击 “Settings”。

步骤二：在左侧菜单中选择 “Pages”。

步骤三：在 “Build and deployment” 部分：

Source 选择 “Deploy from a branch”。

Branch 选择你的主分支（通常是 main 或 master）。

步骤四：点击 “Save”。

步骤五：触发部署：回到你的代码编辑器，随便修改一点东西（比如添加一个 README.md 文件），然后再次提交并推送到 GitHub。这次推送会自动触发 GitHub Actions 开始部署你的网站。

![](img/1d1b4aae3b66046cb381661216f92087.png)

步骤六：获取网站地址：稍等片刻，再次进入 Settings -> Pages，你就能看到部署好的网站地址了！GitHub 会给你一个默认域名，直接访问这个域名就能打开你的游戏网站。

# 5\. 分享你的游戏作品

现在，你可以复制这个网址，发给你的朋友炫耀了！

1.  热身 2：2 小时开发视频下载工具站

1.  项目准备

这次的项目实战，我们准备了两个技术方案：

简易版：直接调用第三方接口，快速实现功能。

进阶版：基于开源项目自己部署服务，挑战更大，但能学到更多东西（涉及服务器部署等知识）。

为了让大家跟上节奏，请务必配合下面的视频一起操作。请点击链接，进入飞书文档观看视频。

AI工具站-教学视频

1.  需求分析

很多做自媒体或社媒营销的朋友，经常需要从抖音、小红书等平台找素材进行二次创作。但平台下载的视频和图片通常都带有水印，后期处理起来非常麻烦。市面上虽然有一些去水印的小程序和网站，但我们为什么不自己开发一个呢？

核心需求点：

.

需要一个简洁的交互界面，可以粘贴分享链接。

.

工具能自动解析链接，并且支持多个主流平台。

.

解析后能展示视频或图片封面，并提供无水印的下载功能。

1.  产品功能设计

我们直接找一个竞品来模仿。比如下面这个网站，它的设计非常简单：一个输入框，一个解析按钮。点击解析后，就显示视频的标题、封面和下载地址。

![](img/d995eec29e622d02df5f1d521b6959a1.png)

我们可以在这个基础上做得更好，比如加上视频封面的预览功能。

1.  技术方案设计

去水印的原理是什么？

其实，平台给视频加水印是在客户端完成的。我们只需要找到服务器返回的原始视频链接，那个链接对应的视频就是不带水印的。本质上，这就是一个爬虫功能。

我们可以画一个简单的技术架构图来理清逻辑：

根据产品需求，我们设计一个经典的 B/S 架构。

方案 A (简易版)：前端页面直接调用第三方去水印 API，快速实现功能。

方案 B (进阶版)：自己部署一个解析 API 服务，完全掌控后端逻辑。

1.  编码实现

# 5.1 方案 A (简易版)

# 5.1.1 注册第三方 API 账号

我们选用这个第三方去水印服务：https://qushuiyin.guijianpan.com/

它的性价比很高，最低套餐 1 元起，非常适合我们开发测试。

.

注册账号后，进入右上角的个人中心进行充值。

![](img/3ad245a17ccc545eb797db5787b42799.png)

.

充值后，点击 API 测试，获取你专属的 API 接口地址（已包含密钥）。调用时，只需要将末尾的视频链接替换成真实的分享链接即可。

![](img/ecda954e7a0524883fd0ad9648217860.png)

# 5.1.2 界面开发与联调

步骤一：用 Postman 测试接口

API 准备好后，我们先用 Postman 测试一下，确保它能正常工作，并看清楚返回的数据结构，这样才能告诉 AI 如何精准地开发。

在 Postman 中创建一个新的请求。

![](img/77ef32291ac987162ad479e28aa6d8e2.png)

![](img/70f3131485dd1d7866ec4dafece2aa61.png)

将从抖音复制的分享文案中的 https:// 开头的链接提取出来。例如，从下面的文案中提取出 https://v.douyin.com/ZOqdo9qsYuY/。

4.89 03/24 cNJ:/ K@W.md 随意“搭讪”韩国美女，印度富人区的三哥能有多自信？ # 外国人 # 歪果仁真会玩 # 印度 # 旅行 # 看世界 https://v.douyin.com/ZOqdo9qsYuY/ 复制此链接，打开 Dou 音搜索，直接观看视频！

将提取出的链接拼接到你获取的 API 地址后面，发送请求。

![](img/25b95a0ff37c3ebe786a9525d4bde4cd.png)

![](img/4bfea6d9ff57e15c0cc0c0a88748471a.png)

不出意外，你就能在下方看到 API 返回的 JSON 数据了。

步骤二：让 AI 开发网站

```
帮我生成一个去水印下载的网站，需求如下：
1\. 暂时不需登录注册，只加一个固定的密码验证，密码 123456
2\. 我们需要一个交互界面，可以粘贴分享链接，用户粘贴的链接如下 4.89 03/24 cNJ:/ K@W.md 随意“搭讪”韩国美女，印度富人区的三哥能有多自信？ # 外国人 # 歪果仁真会玩 # 印度 # 旅行 # 看世界  https://v.douyin.com/ZOqdo9qsYuY/ 复制此链接，打开Dou音搜索，直接观看视频！，需要通过正则提取出http 或者https链接
有一个开始解析按钮，用户点击开始解析就可以根据api返回的数据 展示解析的 标题、视频地址、封面地址，并预览封面
可以下载视频和封面
这是api地址：https://api.guijianpan.com/waterRemoveDetail/xxmQsyByAk?ak=你的秘钥&link=https://v.douyin.com/ZOqdo9qsYuY
这是api返回的数据结构：
content中的cover是封面字段，url是视频或者图片链接，你需要通过前端的方式下载
{
    "accessToken": "",
    "code": "10000",
    "msg": "成功!",
    "content": {
        "author": "",
        "avatar": "",
        "cover": "https://p26-sign.douyinpic.com/tos-cn-p-0015c000-ce/o8UTSAHbv4KjhggioEv4TFAeefM1ZwQH2sYeD7~tplv-dy-resize-walign-adapt-aq:720:q75.webp?lk3s=138a59ce&x-expires=1756515600&x-signature=%2FhPB1b95JwIWcplIBp%2BUI4E1yAw%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=cover&biz_tag=aweme_video&l=20250816093602CF8E8B9092420311F682",
        "coverList": [],
        "headUrl": "",
        "imageList": [],
        "likeNum": 0,
        "msg": "",
        "originText": "https://v.douyin.com/ZOqdo9qsYuY",
        "shortUrl": "https://v.douyin.com/ZOqdo9qsYuY",
        "shuiYinPlatform": null,
        "success": true,
        "title": "随意“搭讪”韩国美女，印度富人区的三哥能有多自信？ #外国人 #歪果仁真会玩 #印度 #旅行 #看世界",
        "type": "VIDEO",
        "url": "https://v9-default.365yg.com/2e3a0ce3b41372f7fe68bd18b4143c7e/689fef86/video/tos/cn/tos-cn-ve-15c000-ce/oIR085Eh9CfIXAL7fJRE1wVRdCBIgreuksvGIs/?a=2011&ch=0&cr=0&dr=0&cd=0%7C0%7C0%7C0&cv=1&br=3144&bt=3144&cs=0&ds=3&ft=aT_7TQQqUYqfJEZPo0OW_QYaUqiXXtqmRVJEjUJEpvPD-Ipz&mime_type=video_mp4&qs=0&rc=ZWRpaTU1ODM8M2ZlZDg6OEBpM3lqaHk5cjplNTMzbGkzNEAxMDJjMi4yXy4xMjIwLS0yYSNqZWhsMmRrby9hLS1kLWJzcw%3D%3D&btag=c0000e00030000&dy_q=1755308162&feature_id=fea919893f650a8c49286568590446ef&l=20250816093602F50CD29B5E9166D76423",
        "videoList": []
    },
    "timestamp": 1755308162803
}
```

几分钟后，代码就生成好了。

![](img/118d3ca548542af7789883000992b927.png)

直接在浏览器中打开预览，测试一下功能。如果发现任何问题或不符合预期的地方，继续让 AI 修改即可。

# 5.2 方案 B (进阶版)

这个方案相对复杂，适合有一定技术基础或喜欢挑战的同学，最好懂一些 Linux 和 Docker 的基础命令。

# 5.2.1 注册服务器

我们使用 DigitalOcean 的云服务器。现在新用户注册送 200 美元信用额度，60 天内可以免费体验。

注册链接： https://m.do.co/c/39f17dfb48be

注册后需要添加支付方式，DigitalOcean 支持支付宝和 Visa 卡，非常方便。

![](img/1471ea15039a399c7df103a37cec3f21.png)

我用的支付宝，比较方便

![](img/c87032ad2e59cd852505bac40ac06849.png)

# 5.2.2 配置服务器

步骤一：在顶部菜单选择 Create -> Droplets，创建一个新的云服务器。

![](img/9bb4afe926ffc344ba6705ee4703a7db.png)

虚拟机创建好之后，我们就可以登录进行服务部署了

![](img/425ab42e0ab2bb37ea965b16c0224f56.png)

步骤二：服务器创建好后，复制它的 IP 地址。

步骤三：在你的电脑终端（Mac 用 Terminal，Windows 用 PowerShell）中，使用 SSH 命令登录服务器：

```
ssh root@你的服务器IP地址
```

然后输入你创建服务器时设置的密码。如果看到系统欢迎信息，就说明登录成功了。

![](img/e0ad3940fd1818c67134caa6283a153a.png)

注意：有时新分配的 IP 在国内无法访问。如果遇到这种情况，要么你开全局 VPN，要么就删掉这台服务器，重新创建一个。

# 5.2.3 使用 Docker 部署服务

我们将使用这个开源项目作为我们的 API 服务：Douyin_TikTok_Download_API

作者已经提供了 Docker 镜像，部署起来非常方便。

步骤一：在服务器上安装 Docker

依次执行以下命令来安装 Docker 环境：

```
# 更新 apt 并安装必要依赖
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg lsb-release

# 添加 Docker 官方 GPG key
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

# 设置稳定版仓库
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

步骤二：安装 Docker

```
sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

![](img/5ceba3ce3503031a6a0736a383660618.png)

步骤三：验证 Docker 是否安装成功

执行以下命令，如果能看到版本号，就说明成功了。

```
docker --version
docker compose version
```

![](img/ecfd4b2aff8b653312cc3ef4d37ad7a9.png)

步骤四：拉取 API 镜像并运行容器

拉取最新的镜像：我们可以直接拉取 Douyin_TikTok_Download_API 镜像到服务器

```
docker pull evil0ctal/douyin_tiktok_download_api:latest
```

![](img/6ac25da596961393a80f1a44b39f43dd.png)

运行容器：拉取镜像后，您可以从此镜像启动一个容器。以下是运行容器的命令，包括基本配置：

```
docker run -d --name douyin_tiktok_api -p 80:80 evil0ctal/douyin_tiktok_download_api
```

这个命令的每个部分作用如下：

-d：在后台运行容器（分离模式）。

--name douyin_tiktok_api ：将容器命名为douyin_tiktok_api 。

-p 80:80：将主机上的 80 端口映射到容器的 80 端口。根据您的配置或端口可用性调整端口号。

evil0ctal/douyin_tiktok_download_api：要使用的 Docker 镜像名称。

步骤五：验证容器是否运行

执行 docker ps 命令，如果能看到 douyin_tiktok_api 正在运行，就说明服务部署成功了。

```
docker ps
```

![](img/a9aa9a0078218ffa80511605ebd03f43.png)

我们可以看到容器已经运行并监听在 80 端口了

现在，直接用服务器 IP 访问，就能看到项目自带的 Web 界面了。不过我们的目的是使用它的 API。

![](img/fa338146dd63cc6a2981cf7b68699700.png)

![](img/0b0ee22533c3de9bbc05a42e9b7b1020.png)

步骤六：配置服务（重要）

这个 API 服务需要配置你自己的抖音 Cookie 才能正常工作。

以下是Cookie

![](img/add900aa426c6e00730a636b693f2bda.png)

首先，进入容器内部：

```
 # 进入容器
 docker exec -it 951f3ab723df bash
```

容器里没有文本编辑器，需要先安装一个 vim：

```
apt update
apt install vim -y
```

根据项目文档的指示，找到配置文件并填入你自己的 Cookie。

![](img/18d9636c65867f1936d8fff6da5eb068.png)

步骤七：测试 API

根据 API 文档，我们需要分两步调用：

第一步： 通过 /api/douyin/web/get_aweme_id 接口，传入分享链接，获取视频的 aweme_id。

第二步： 通过 /api/douyin/web/fetch_one_video 接口，传入 aweme_id，获取视频的详细信息（包括无水印下载地址）。

然后把我们的服务器 IP+接口路径 就是我们的 API 地址

http://68.183.189.191/api/douyin/web/get_aweme_id?url=https://v.douyin.com/ZOqdo9qsYuY/

用 Postman 测试一下，确保能成功获取到数据。

![](img/728b6007841bf980dc94b0e46039bb8d.png)

可以成功获取到视频信息了

步骤八：让 AI 修改前端代码

现在，把最新的 API 地址、调用流程和数据结构再给 AI，让它重新修改前端代码。Prompt 可以这样写：

```
我先需要替换视频解析的API，获取流程也有变化，你需要先通过 这个接口获取 aweme_id http://152.42.210.73/api/douyin/web/get_aweme_id
然后通过这个接口获取视频信息，用get请求 http://152.42.210.73/api/douyin/web/fetch_one_video
入参是： aweme_id：  作品id/Video id
这是视频信息的数据结构, 下载地址取download_addr 中的 第一个 ：
{
    "code": 200,
    "router": "/api/douyin/web/fetch_one_video",
    "data": {
        "aweme_detail": {
            "cover_url": "https://p3-pc-sign.douyinpic.com/image-cut-tos-priv/f715424fb432b1e04d7eaa8a682bd6c9~tplv-dy-resize-origshort-autoq-75:330.jpeg?lk3s=138a59ce&x-expires=2070691200&x-signature=LLZjf2y9xMKq%2Fno8OmIoq2%2BCn4k%3D&from=327834062&s=PackSourceEnum_AWEME_DETAIL&se=false&sc=cover&biz_tag=pcweb_cover&l=20250816163832CBE436E3F1F51A29206C",
            "desc": "随意“搭讪”韩国美女，印度富人区的三哥能有多自信？ #外国人 #歪果仁真会玩 #印度 #旅行 #看世界",
            "video": {
                "download_addr": {
                    "data_size": 124010130,
                    "file_cs": "c:0-261633-e63a",
                    "height": 720,
                    "uri": "v1e00fgi0000d22br7nog65voekghvm0",
                    "url_list": [
                        "https://v3-dy-o.zjcdn.com/c96f32aebf4d0d875e3c950c587b39e6/68a06eac/video/tos/cn/tos-cn-ve-15c800-ce/o4gsjQXQRJhmvf9fAMCleiGCXjsQ8I874BqDEY/?a=6383&ch=26&cr=3&dr=0&lr=all&cd=0%7C0%7C0%7C3&cv=1&br=3916&bt=3916&cs=0&ds=3&ft=~MeSYs809o0PD1tvSz7g9wG8albvEeC~P5&mime_type=video_mp4&qs=0&rc=ZjNmOzNlOTk2Nmc7PGZnOkBpM3lqaHk5cjplNTMzbGkzNEBgMWJiMmJhNjMxNWAyMjAzYSNqZWhsMmRrby9hLS1kLWJzcw%3D%3D&btag=80000e00030000&cc=1f&cquery=100x_100z_100o_100w_100B&dy_q=1755333512&feature_id=dc6e471fd69cf67451806384e04f2b47&l=20250816163832CBE436E3F1F51A29206C&req_cdn_type=",
                        "https://v3-dy-o.zjcdn.com/c96f32aebf4d0d875e3c950c587b39e6/68a06eac/video/tos/cn/tos-cn-ve-15c800-ce/o4gsjQXQRJhmvf9fAMCleiGCXjsQ8I874BqDEY/?a=6383&ch=26&cr=3&dr=0&lr=all&cd=0%7C0%7C0%7C3&cv=1&br=3916&bt=3916&cs=0&ds=3&ft=~MeSYs809o0PD1tvSz7g9wG8albvEeC~P5&mime_type=video_mp4&qs=0&rc=ZjNmOzNlOTk2Nmc7PGZnOkBpM3lqaHk5cjplNTMzbGkzNEBgMWJiMmJhNjMxNWAyMjAzYSNqZWhsMmRrby9hLS1kLWJzcw%3D%3D&btag=80000e00030000&cc=1f&cquery=100o_100w_100B_100x_100z&dy_q=1755333512&feature_id=dc6e471fd69cf67451806384e04f2b47&l=20250816163832CBE436E3F1F51A29206C&req_cdn_type=",
                        "https://www.douyin.com/aweme/v1/play/?video_id=v1e00fgi0000d22br7nog65voekghvm0&line=0&ratio=540p&watermark=1&media_type=4&vr_type=0&improve_bitrate=0&biz_sign=NRPI1lC4AlkgB1YZ_o3IkPAfESQSvePEcuaR9NwmI3OwTcZpH5ZUm80f5LmE9VaaOzLa7CA0Ou-V1V2BgVoXftUQ6E7HDGbNHaUZIZuaRMUGyO7s5wbVW7et0I2xs1hA&logo_name=aweme_search_suffix&source=PackSourceEnum_AWEME_DETAIL"
                    ],
                    "width": 720
                }
            }
        }
    }
}
```

代码修改好之后，我们再来测试

![](img/13ccecc84ddb3298eb18db9d26663dd5.png)

我们发现会遇到一个跨域请求的问题。

什么是跨域？ 简单说，就是浏览器出于安全考虑，默认禁止网页向不同域名、协议或端口的服务器发起请求。

要解决这个问题，我们需要再次进入容器，修改 app/main.py 文件，添加允许跨域的响应头。然后重启 Docker 容器，让配置生效。

```
from fastapi.middleware.cors import CORSMiddleware

# 允许的前端来源（域名）
origins = [
    "*",   # React/Vue 本地开发
]

# 添加 CORS 中间件
app.add_middleware(
    CORSMiddleware,
    allow_origins=origins,            # 允许的源
    allow_credentials=True,           # 允许携带 Cookie
    allow_methods=["*"],              # 允许所有请求方法：GET、POST...
    allow_headers=["*"],              # 允许所有请求头
)
```

然后加入允许跨域代码

![](img/d7e129fd5afcd8e74c8f7fc64eef1668.png)

：wq 保存并退出

重启 docker 容器

接口已经替换为我们自己部署的 API 服务

1.  部署上线

后端服务已经部署好了，现在我们来部署前端页面。你可以继续使用之前的 GitHub Pages，或者直接把前端也部署到我们的服务器上。

步骤一：重新打开一个本地终端，使用 scp 命令将前端代码目录复制到服务器上：

```
scp -r ./VideoDownloader root@你的服务器IP:/home
```

![](img/14091411af60c854ff1d948b63d05070.png)

步骤二：登录服务器，进入代码目录，并使用 Python 启动一个简单的 Web 服务来托管前端页面：

```
cd /home/VideoDownloader
nohup python3 -m http.server 8000 > server.log 2>&1 &
```

这条命令会在后台启动一个监听 8000 端口的 Web 服务。

步骤三：现在，通过 http://你的服务器IP:8000 就可以访问你的视频下载工具站了！

![](img/0fb646911fba6ddea60748bc0e1fd361.png)

![](img/908e1ebfdd98ad6a69fd265dd5fada07.png)

1.  产品开发的流程

# 1\. 本章概要

本章主要探讨作为独立开发者，如何完整地走通产品开发的整个过程。

我们将学习如何从发现用户需求开始，通过敏捷开发模式快速构建并验证产品（MVP）。

技术方面，会重点介绍全栈 JavaScript 开发（特别是 Next.js 框架）、AI 辅助编程和实用的调试技巧。

此外，还会涵盖产品上线后的持续交付（CI/CD）、用户增长策略，以及如何根据用户反馈和数据不断优化产品，实现有效迭代。

简单来说，本章就是教你怎么找到好点子，用最快的方法把它做出来，上线后怎么让更多人用、怎么赚钱，最后怎么不断改进，让产品越来越好。

⭐️本章内容比较庞杂，截图和文字能传达的信息有限，所以我特意录制了视频，请大家配合使用。

请点击下方链接，进入飞书文档观看视频。

AI工具站-教学视频

# 本章航线图

完成本章节的学习和实操，即可完成航线图的：

第三阶段：运营与商业化（约 7 天）

1.  需求挖掘：学习用户调研与竞品分析，明确产品方向（约 2 天）。

1.  流量运营：掌握 SEO 和社媒营销策略，提升网站流量（约 2 天）。

1.  变现策略：实践 Stripe 支付接入与产品订阅设计（约 2 天）。

1.  持续迭代：收集用户反馈并优化产品功能（约 1 天）。

1.  产品开发流程

一般互联网公司的产品开发流程是：需求 -> 设计 -> 研发 -> 测试 -> 上线 -> 运营 -> 迭代。每个环节都有专门的团队负责。

但对于咱们独立开发者或小团队来说，所有流程可能都得一个人搞定。这意味着，独立开发者需要具备从想法 -> 产品 -> 技术 -> 部署 -> 用户 -> 变现的全链路能力。

别怕，这些能力不是天生的，可以通过不断学习和实战慢慢积累。我们这次航海的目的，就是帮助大家补齐短板，发挥优势，完成从量变到质变的积累。

独立开发者更适合敏捷开发模式。

敏捷开发 (Agile Development) 的核心思想是：以用户价值为中心，通过快速迭代，持续交付可用的软件，而不是等所有功能都做完再一股脑上线。

尤其是在 MVP (最小可行产品) 阶段，我们不需要开发全部功能，而是快速开发一个最小可用的核心功能来验证我们的想法，然后根据用户的真实反馈来不断迭代优化。

虽然我们是单兵作战，但该有的流程还是要有的。我们要像盖大楼一样，先打好坚实的地基（技术基础和规范），才能保证上层建筑的可靠。在经验不足时，我们可以先从盖几个“小房子”开始，积累了技能和经验后，再去挑战“摩天大楼”。

1.  必要的技术基础

1.  什么是全栈开发？

这次航海我们不会讲太多的技术理论，但是设计到产品开发的基础还是需要了解的。

全栈开发 (Full-Stack Development) 指的是一个开发者既能搞定前端（用户看到的界面），也能搞定后端（处理业务逻辑和数据），甚至还能处理数据库、服务器运维等工作。简单来说，全栈开发者就是能独立完成一个完整产品功能的多面手。

作为独立开发者，掌握全栈开发是必须的。好在现在有了 AI 的辅助，极大地降低了全栈开发的门槛。我们可以边做边学，先行动起来最重要。

通常，全栈开发主要指能独立完成前端和后端。

前端一般负责用户界面、交互逻辑的开发

技术栈：HTML、CSS、JavaScript、TypeScript

框架：React、Vue、Angular、Next.js、Nuxt.js

移动端：React Native、Flutter

后端一般负责实现业务逻辑、接口、权限、安全

技术栈：Node.js、Python（Django/FastAPI）、Java（Spring Boot）、Go、PHP

REST API / GraphQL

你可能注意到了，前端和后端技术栈里都出现了 JavaScript (JS)。Node.js 的出现，让 JS 不再局限于浏览器，也可以在服务器上运行。这意味着，我们可以用同一种语言（JS）来完成前端和后端的全部开发，这就是 JS 全栈。

用 JS 做全栈的好处是“快”：

学习快：只需掌握一门语言。

迭代快：前后端代码可以复用，生态系统统一（都用 npm 包）。

上线快：非常适合独立开发者和小团队快速验证想法。

我们这次航海主要使用的技术栈就是 React + Next.js。

主要用到的框架 React + Nextjs

React 是由 Facebook（Meta）开发的一个 前端 JavaScript UI 库。

主要用于构建 用户界面（尤其是单页应用 SPA）。

特点：

组件化：页面由一个个独立的组件组成，方便复用和维护。

虚拟 DOM：提升页面渲染性能。

单向数据流：数据从上到下传递，逻辑清晰。

生态丰富：配合 React Router、Redux、Tailwind 等可搭建完整前端应用。

简单说，React 只负责 前端视图层，像一块“拼图工具”，你得自己拼出完整应用。

Next.js 是基于 React 的 全栈框架。

由 Vercel 开发，弥补了 React 的不足。

特点：

SSR（服务端渲染）：页面在服务器渲染，首屏加载更快，对 SEO 友好。

SSG（静态站点生成）：能在构建时生成静态页面，性能更佳。

API Routes：直接写后端 API（比如 /api/user），实现前后端一体化。

路由自动化：基于 pages/ 文件夹的目录结构自动生成路由。

全栈能力：不仅能做前端，还能写后端接口，是真正的 React 全栈框架。

简单说，Next.js = React + 服务端渲染 + 路由系统 + API 支持。

虽然大部分开发工作可以交给 AI，但掌握一些基础语法还是很有必要的，至少要能看懂 AI 生成的代码，关键时刻才能自己动手调试。

1.  一天入门 JavaScript 教程

JS 代码可以直接在浏览器里测试和执行。只需打开一个空白页，右键“检查”打开开发者工具，在 Console (控制台) 面板里就可以输入代码并看到结果。

![](img/0580937d5e2b56addf91608c26313eed.png)

![](img/a50b1cfaae003455fb7308dccf1f0bbd.png)

# 基础语法

.

JavaScript 是什么

一种运行在浏览器和服务器（Node.js）的编程语言

用来实现网页交互、逻辑和后端处理

.

Hello World

这是 HTML 代码 只需要新建个文本文件，保存成。html 在浏览器打开就行了

```

我的第一个JS 

```

.

变量和常量

```
let name = "Tom";   // 可变
const age = 18;     // 常量
var oldWay = "不推荐"; // 老写法
```

.

数据类型

字符串： "hello"

数字： 123

布尔： true / false

数组： [1, 2, 3]

对象： {name: "Tom", age: 18}

null / undefined

```
let arr = [1, 2, 3];
let person = {name: "Tom", age: 18};
console.log(arr[0]); // 1
console.log(person.name); // Tom
```

# 逻辑与函数

.

运算符

```
console.log(5 + 2);  // 7
console.log(5 > 2);  // true
console.log("5" == 5);  // true (宽松比较)
console.log("5" === 5); // false (严格比较)
```

.

条件语句 (if...else)

```
let score = 80;
if (score >= 90) {
  console.log("优秀");
} else if (score >= 60) {
  console.log("及格");
} else {
  console.log("不及格");
}
```

.

循环 (for)

```
// 打印 0 到 4
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

.

函数 (function)

```
// 定义一个函数
function add(a, b) {
  return a + b;
}
// 调用函数
console.log(add(3, 5)); // 输出 8

// 箭头函数 (更现代的写法)
const multiply = (a, b) => a * b;
console.log(multiply(2, 4)); // 输出 8
```

# DOM & 事件

.

操作 HTML 元素 你可以用 JS 来改变网页上的内容。

```
Hello

```

.

事件监听

# 进阶 & 实战

.

数组方法

```
let nums = [1, 2, 3, 4];
let doubled = nums.map(n => n * 2);   // [2,4,6,8]
let filtered = nums.filter(n => n > 2); // [3,4]
let sum = nums.reduce((a, b) => a + b, 0); // 10
```

.

异步（Promise & async/await）

```
function getData() {return new Promise(resolve => {setTimeout(() => resolve("数据加载完成"), 1000);
  });
}

async function show() {let result = await getData();console.log(result);
}
show();
```

.

小项目：计数器

```
0

```

# 最后总结一下学习目标

理解语法，能写简单逻辑

掌握函数和条件循环

能操作网页内容，做按钮交互

理解数组操作、异步，写个小 demo

1.  React / Node.js 入门速成教程（一天）

# 3.1 Node.js 入门：创建你的第一个服务器

Node.js 代码需要 Node 环境来执行。把代码保存为 .js 文件，然后在终端用 node 文件名.js 来运行。

创建一个简单的 HTTP 服务器：

步骤一：新建一个文件 server.js。

步骤二：写入以下代码：

```
// 引入 http 模块
const http = require("http");

// 创建服务器
const server = http.createServer((req, res) => {
  res.writeHead(200, { "Content-Type": "text/plain" });
  res.end("Hello from Node.js server!");
});

// 监听 3000 端口
server.listen(3000, () => {
  console.log("服务器运行在 http://localhost:3000");
});
```

步骤三：在终端运行：node server.js

步骤四：打开浏览器，访问 http://localhost:3000，你就能看到 "Hello from Node.js server!" 了。

# 3.2 React 入门：创建你的第一个组件

我们推荐使用 Vite 来快速创建 React 项目。

步骤一：在终端执行以下命令：

```
# 创建项目
npm create vite@latest my-react-app -- --template react
# 进入项目目录
cd my-react-app
# 安装依赖
npm install
# 启动开发服务器
npm run dev
```

步骤二：浏览器会自动打开 http://localhost:5173。

步骤三：打开 src/App.jsx 文件，这就是 React 的核心——组件。

JSX: 允许你在 JS 里像写 HTML 一样写界面。

State (状态): 用来存储和管理组件的数据，当 state 改变时，界面会自动更新。

一个最小的计数器示例：

```
import { useState } from "react";

function App() {
  // 'useState(0)' 创建一个名为 count 的 state，初始值为 0
  const [count, setCount] = useState(0);

  return (

# Hello React

当前计数：{count}

      {/* 点击按钮时，调用 setCount 来更新 count 的值 */}

  );
}

export default App;
```

1.  进阶：Next.js 简介

Next.js 是 React 的全栈框架，它帮你把前后端都整合好了。

服务端渲染 (SSR)：页面在服务器上就渲染好了，对 SEO 和首屏加载速度非常友好。

API Routes: 可以在 pages/api/ 目录下直接写后端接口。

快速创建 Next.js 项目：

```
npx create-next-app my-next-app
cd my-next-app
npm run dev
```

创建一个后端接口 pages/api/hello.js：

```
export default function handler(req, res) {
  res.status(200).json({ text: "Hello from Next.js API" });
}
```

现在，你就可以在前端组件里通过 fetch('/api/hello') 来调用这个后端接口了。

```
useEffect(() => {fetch("/api/hello")
    .then(res => res.json())
    .then(data => setMsg(data.text));
}, []);
```

# 5\. AI 辅助开发

得益于大模型的飞速发展，AI 编程工具已经从一个简单的代码片段生成器，进化到了一个“实习生水平”的开发伙伴。在我们的实际项目中，通过 AI 编程，开发效率提升了近 10 倍。

比如这个项目中，在 5 月份的是，我一个月只能提交 6k 行代码，到了 7 月份在 AI 的辅助下，提交了近 3w 行代码。当然我们开发的不只这一个项目，同时有几个项目开发。

![](img/62366ac0f85e91df09e84ecc709bc503.png)

在另一个项目里，也提交了 3w+行代码

AI 不仅能写代码，还能帮你生成原型图、UI 稿，能力越来越全面。

![](img/5dad8e581dc99cecf33f67ae90a5683b.png)

![](img/b34d0972aecc17b7173e632390316367.png)

我常用的 AI 编程工具有 Trae 和 Claude Code。Trae 是 Fork 的 VSCode 修改的，界面交互跟 VSCode 类似，字节出品交互设计还比较符合操作习惯，它里面集成了很多模型，最好用的还是 Claude4。

![](img/579af18edffce78681f1234fc90dcce1.png)

它比较好用的地方在于你可以把某段代码或某个文件添加到提示词中，让 AI 精准的修改代码，不过这个随着 Claude Code 插件的更新，这个优势已经没了。

另一个好用的地方在于它修改代码后会让你选择需要修改的地方，如果不满意可以撤销。

![](img/da11dbc5032fb5209f960fd69451394a.png)

最近 Trae 又更新了一个 Solo 模式（Solo 模式使用条件：

.

充值成为 pro 用户

.

需要获取邀请码（目前很难拿到）），就是可以从编码到上线部署一条龙服务，AI 会先理解你的需求，并设计开发文档，然后编码，再链接数据库创建数据表，然后发布上线，官方说法是从插件进化成了一个 AI 工程师，但是体验了一下感觉就是集成了一些固定的工作流，比如发布是集成了 Vercel， 数据库是集成了 Supabase， 估计还不能登录服务器部署等，不过对要求不高的开发者来说已经比较方便了。

![](img/e0ce2d403d9f18cc7cf935b8693e9c80.png)

这是 Solo 模的界面

![](img/e64c56463f808602c8b66108c8e1237d.png)

Claude Code 没有界面，它只是一个命令行工具 (CLI)，虽然没有图形界面，但功能极其强大。它可以理解你的整个项目，进行跨文件重构，速度快，效果好，这主要得益于它超长的上下文处理能力。

我们会在后面的章节详细讲解如何使用这些工具。

# 6\. 前后端调试技巧

AI 毕竟不是万能的，有时也会“犯傻”。当它搞不定时，就需要我们自己动手调试了。掌握一些基本的调试技巧至关重要。

# 6.1 前端调试 (浏览器开发者工具)

a.断点调试

· 打开 Sources 面板 → 在代码行号处点击加断点。

· 支持条件断点（右键 → “Add conditional breakpoint”）。

· 常用场景：只在变量满足某条件时停下。

b.监视变量（Watch Expressions）

· 在调试面板添加变量，实时观察值的变化。

c.逐步执行

· Step over （F10）：逐行执行。

· Step into （F11）：进入函数内部。

· Step out （Shift+F11）：执行到函数结束返回。

![](img/228c31b4af244b2067656f0c036aba8e.png)

d.网络请求调试（Network 面板）

· 查看请求是否成功（状态码、请求头、响应体）。

· 过滤 XHR/fetch 请求，调试接口调用。

· Replay XHR：重复发送请求。

![](img/5c50940b286e74841046b3408900cbb5.png)

e.本地存储调试（Application 面板）

· localStorage / sessionStorage / cookies / IndexedDB.

· 常用来模拟登录态、修改缓存数据。

f.调试样式（Elements 面板）

· 实时修改 CSS 样式。

· 追踪 DOM 节点变化（右键 → Break on → attribute modifications）。

![](img/e516d7ace523eeabf4bda2f9690435e6.png)

小问题 → console / 断点

中等问题 → Network / Application / Source Map

复杂问题 → 性能分析 / 移动端远程调试 / Mock API

线上问题 → 日志 & 错误监控

# 6.2 后端调试

# 6.2.1 基础调试技巧

a.日志调试（最常用）

console.log / print / logger.info 等输出关键变量。

日志分级：DEBUG、INFO、WARN、ERROR、FATAL。

建议用专业日志库（如 winston、log4j、pino），支持 JSON 格式化和日志轮转。

b.断点调试

在 IDE（VSCode、IntelliJ、PyCharm 等）里设置断点。

逐步执行函数、查看变量值、调用栈。

常用于复杂业务逻辑或难以定位的 bug。

c.使用调试工具 / REPL

Node.js → node inspect 或 ndb。

Python → pdb / ipdb.

Java → JDWP 协议，远程 attach 调试。

# 6.2.2 后端特有调试技巧

1.接口调试

用 Postman / Insomnia / curl 模拟请求，验证接口逻辑。

配合 Fiddler / Charles 抓包工具调试 HTTP/HTTPS 请求。

2.数据库调试

在 SQL 执行前后打印 SQL 和参数。

慎用 ORM 的 lazy load，调试时可开启 SQL 日志。

使用事务回滚测试逻辑，避免污染真实数据。

3.远程调试

在服务器运行时 attach 调试器（Java: -agentlib:jdwp，Node: --inspect）。

Docker 容器内可用 docker exec -it + 调试工具进入环境。

4.配置与环境调试

打印当前加载的配置文件和环境变量。

常见 bug：本地 dev 配置和 prod 配置不一致。

用 .env 或配置中心管理环境。

# 7\. 持续交付 CI/CD

我们的产品需要不断迭代，可能一天要发布好几次。如果每次都手动打包、上传服务器，那也太低效了。CI/CD (持续集成/持续部署) 就是来自动化这个流程的。

CI (持续集成)：当你把代码提交到 GitHub 后，会自动触发构建和测试，确保新代码没有引入 bug。

CD (持续部署)：一旦代码通过了所有测试，就会自动部署到服务器上，实现一提交代码就立即上线的爽快体验。

我们这次航海会用到两种 CI/CD 工具：

Vercel: 自带 CI/CD 流程，对于 Next.js 项目来说，配置简单，开箱即用。

GitHub Actions: 功能更强大、更灵活，可以自定义任意复杂的部署流程，比如部署到你自己的服务器。

![](img/48cc3abade9367f7a5d9872bac1a9ca6.png)

Github 给每个账号的每个月免费额度是 500 分钟，这项目设置可以查看自己的使用时长和任务数量

1.  AI 编程入门

# 1\. AI 编程发展

AI 编程工具已经经历了飞速的进化：

早期 (GPT-3 时代)：通过网页问答或 API 生成代码片段，交互体验有限。

中期 (Copilot 时代)：以 VS Code 插件形式出现，能根据上下文自动补全代码，交互更自然。

现在 (Agent 时代)：以 Cursor、Trae、Claude Code 为代表，它们能理解整个项目，进行跨文件的重构、调试，甚至执行部署命令，形成了一个完整的开发闭环。

AI 编程能力的核心限制之一在于上下文长度。模型能一次性“看到”的代码越多，对你意图的理解就越准确。Claude Code 的巨大优势就在于其超长的上下文管理能力，这也是它在处理复杂任务时表现出色的重要原因。

# 2\. AI 编程工具使用

# 2.1 Trae

Trae 的核心功能在于其直观的交互和精准的上下文引用。

Chat 模式：你可以像和人聊天一样，对代码库提问，获取建议或优化方案。

上下文引用：在对话中，你可以用 @ 符号引用某个文件或整个项目，让 AI 的修改更精准。

代码变更预览：AI 修改代码后，会以 diff 的形式让你预览，你可以选择接受或拒绝修改，非常安全。

![](img/aae9ca916aeac6dd4f321f3d9a3602eb.png)

# 2.2 Claude Code

# 2.2.1 什么是 Claude Code?

理解整个代码库（不仅仅是当前文件）

执行跨文件的重构、调试

帮你写 PR、运行测试、修复 bug

与 Git、CI/CD、数据库、API 等工具链深度协作

用自然语言交互，让 AI 成为你代码仓库的“伙伴”

独特的代码理解方式

与传统编程 AI 工具不同，Claude Code 在理解代码库时，不进行任何形式的索引或 RAG（检索增强生成）。

它的工作方式更像一个新人加入团队后熟悉项目的过程——通过探索来理解，称之“智能体式搜索”。它会使用 glob、grep、find 等命令在代码库中穿梭，阅读文件，理解项目结构和逻辑。

这意味着模型可以先进行一次搜索，然后根据搜索结果判断：“嗯，我可能还需要了解另外几件事。” 于是它会进行更多的搜索，逐步构建起对整个代码库的认知。

![](img/e20c92e05746831abe847d91b35f99df.png)

# 2.2.2 Claude 使用技巧

1.  项目初始化 (/init)

用 Claude Code 写新项目时，需要先通过 /init 命令来初始化项目，让 CC 先理解整个项目的业务逻辑、功能、使用的技术栈、启动方式等，后续执行任务时 CC 会自动加载这个文件，从而读取项目信息。

CLAUDE.md 是一个特殊文件，Claude 在发起对话时会自动将其拉入上下文中。

也就是说，它可以存储如下信息：

项目的业务逻辑

核心文件和实用函数

代码风格指南、存储库规则

开发者环境设置、测试说明

项目特有的任何意外行为或警告

其他信息

![](img/869c50bb081f9934267bc95d80e063da.png)

1.  常用命令

.

/init：生成 CLAUDE.md 项目记忆文件

.

/clear：清空会话历史

.

/compact：压缩会话历史

.

/model：切换模型

.

/permissions：查看/更新权限

.

/status：查看账户 / 系统状态

.

/resume : 恢复对话

1.  自动模式

```
claude --dangerously-skip-permissions
```

在 Claude Code CLI 里，--dangerously-skip-permissions 是一个跳过权限检查的标志

Claude Code 在执行某些操作时（例如 读写文件、运行 shell 命令、调用外部工具），默认会弹出权限提示，让你确认是否允许执行。

这样做的目的是 安全防护：防止 AI 在你不知情的情况下修改关键文件、删除数据或执行危险命令。

--dangerously-skip-permissions

启用后，Claude Code 将 不再询问你，直接执行它认为需要的操作。

它会：

直接访问/修改文件；

直接运行 Bash 命令；

直接调用已配置的 MCP 工

1.  提示词技巧

.

规则约束：

CC 同样存在 AI 的通病，有幻觉、一本正确的胡说八道、自作聪明、喜欢 Mock 数据、喜欢模拟结果、喜欢写冗余代码等等新手会存在的问题，所以我们需要在 CLAUDE.md 中给 CC 一些约束规则，比如你的编码风格、你喜欢的技术栈等

![](img/011db972388bcf2c2f09e095d212cbf3.png)

.

善用上下文

Claude Code 支持读取当前目录的全部代码，所以建议在项目根目录启动，这样它能更准确理解依赖关系。

.

分步描述复杂任务

如果任务过大，建议分解成多个小步骤，让 Claude Code 逐步完成，减少错误率。

.

有效管理上下文

模型拥有 20 万 token 的超大上下文窗口，但在长时间的会话中仍有可能被填满。

当右下角出现上下文即将用尽的警告时，你有两个选择：

/clear：清空当前会话，重新开始。

/compact：它会启动一个内部提示，让模型将当前会话的所有工作总结成一份摘要，然后用这份摘要作为新会话的“种子”，让你无缝地继续工作。

.

构建高效工作流

先计划，后执行：

不要直接命令“修复这个 bug”，而是说：

我遇到了这个 bug，请先调查原因，然后给我一个修复计划。

这样你可以在它动手前验证其思路是否正确。

利用待办事项 （To-Do List）：在处理复杂任务时，Claude 会生成一个待办事项列表。你可以观察这个列表，如果发现方向不对，可以随时按 Escape 键打断它，并调整计划。

拥抱测试驱动开发 （TDD）：让 Claude 进行小范围修改、运行测试、检查代码规范、然后提交。这种小步快跑的方式能确保项目不会偏离轨道。

利用多模态能力：你可以随时粘贴截图，或者让 Claude 读取图片文件（如 mock.png），并根据视觉设计来构建界面。

.

结合 Git 代码保护

我们在开发时要利用 git 的能力来确保 CC 每次修改代码的最小变动，即便有一次改动是错误的，我们也可以通过 git 版本管理快速恢复代码。

使用 stash 暂存确认最小提交

使用 commit 提交完整功能

比如我们在开发一个完整功能时，可能需要分成多个任务完成，或者 CC 一次写的效果未达到你的要求，需要多次修改，那么如何 review 它每次修改的代码，我可以先把代码提交到暂存区，review 之后再统一提交 commit。

![](img/c00f8f1c9e998be9cae9dec88d778e46.png)

1.  需求挖掘

找准用户需求，你的产品就成功了一半。这里介绍几种实用的需求挖掘方法：

1.  发现身边的需求

最直接的方式，就是解决自己或周围人的痛点。

自己的需求：你自己在使用某个产品时遇到的不便、吐槽，都是绝佳的产品机会。因为你就是目标用户，对需求的理解最深刻。

周围人的需求：多听听朋友、同事的抱怨。他们对某些产品的吐槽，往往隐藏着未被满足的明确需求。

1.  榜单选品

这个思路类似于电商选品。我们可以去 Toolify 这类 AI 工具导航网站，查看月度榜单。

找新品：尽量关注排名 100 以后的产品，这里面更容易发现近期快速增长的新产品。

分析流量：看它的流量来源，如果自然搜索流量占比高（比如高于 50%），说明这个方向有较大的市场搜索需求。

模仿和超越：选择那些你技术上能实现的产品，快速模仿，并思考如何做得比它更好。

![](img/7da53095ef03306de2b41397b05e0996.png)

1.  竞品分析挖掘需求

如果你已经有了一个大概的方向，但不确定是不是伪需求，那就去找对标的竞品。

研究商业模式：看它是靠广告赚钱，还是靠付费订阅。

研究流量渠道：看它的流量是买来的（付费广告），还是自然来的（SEO、口碑）。

判断需求真伪：如果你的竞品有流量，能变现，那基本可以确定这是一个真实存在的市场需求。

![](img/03256b2a2f2d33488d2f8d85f9323e7c.png)

![](img/7ae4cd96d7c8f922c75b329e913bbecd.png)

1.  MVP 验证

《精益创业》的核心原则是：从假设开始，而不是从产品开始。我们找到的需求，大多是我们自己的猜测和假设。关键在于，我们要用最低的成本去验证这些假设。

1.  构建 MVP

MVP 的核心是“最小”和“可行”。我们不需要开发一个完美的产品，只需要开发一个能解决最核心痛点的、最简陋的版本，然后快速推向市场，用真实用户的反馈来验证我们的想法。

比如，Dropbox 早期甚至没有开发产品，只是拍了一个演示视频来介绍它的理念，结果一夜之间获得了数万名意向用户，成功验证了市场需求。

我们开发的第一版产品可能很简陋，问题也很多，但这没关系。关键是把它推出去，找到第一批种子用户，验证我们的想法是否正确。

![](img/7d67b57e87b619d2199a360420882bfe.png)

1.  数据收集与分析

数据是产品优化的指南针。我们需要通过数据来判断我们的假设是否正确。

# 2.1 产品不同阶段的核心数据关注点

了解了这些可观测性的数据指标，我们又该如何收集？

可以通过一些数据统计分析工具

# 2.1.1 用户数据收集

1\. 百度统计：https://tm.baidu.com/

国内免费好用的网站流量分析工具，可以清晰地看到网站的 UV (独立访客)、PV (页面浏览量)、新老用户比例、流量来源等。

![](img/903bf22528446f836b2ca2ed20bdf268.png)

![](img/f94853146ce9e297c90882a09624cb23.png)

![](img/25ffc42f066e1b7dc9ef06b3273005af.png)

这些数据都能反映出你的网站的一些表现，比如 UV 可以反映你每天的流量有多少，有多少时新用户，如果你正在做增长那就需要重点关注这个数据，搜索的关键词和外链可以反映出你 SEO 的效果。

我们这个官网的搜索词基本都是品牌词，说明 SEO 做的不好，没有产品关键词排名。

外链可以反映你做推广的效果，比如这里面经常会有一些 Doubao 或者 Kimi 的来源，说明 AI 给你推荐的流量，就是最近比较流行的 GEO。

2.Umami：https://us.umami.is/

也是我比较喜欢的一个统计工具 开源可以私有化部署

![](img/e754552a143f9c581f69fc0e8643c6ce.png)

3.Google Analytics：https://analytics.google.com/

它的功能就比较强大，能帮助你了解用户行为、流量来源、转化路径等，从而优化产品与营销。

![](img/62ed140076edade99ed8f3365a548e18.png)

![](img/0b104d83029280cb33494eab99178025.png)

![](img/550e36257101e4d35601fa3deb57f259.png)

4\. Microsoft Clarity: https://clarity.microsoft.com/projects 热度地图和用户行为录像

Clarity 是微软提供的一个监控用户行为的免费工具，我们只需要注册接入网站就可以

# 2.1.2 用户反馈收集

首先我们可以在产品中加入反馈入口，引导用户对你的产品功能进行反馈，比如这个功能好不好用，有没有 bug。

![](img/2c097543827f941f471cff208e804148.png)

![](img/a9332503778ddc23f8169b039ce6296f.png)

更进一步，我们是借助扣子开发了一个 AI 客服，

如果是关于产品功能的咨询，AI 客服会先查询产品知识库，可以即时解决用户的问题，这样即可以提升用户体验又能降低运营成本，

因为纯人工客服是很消耗时间的，每天至少要消耗 0.5 人天在客服上，而且大部分都是一些基础的咨询，

我们接入 AI 客服后，人工客服的进线率降低了 70%，每天只需要回复 bug 排查问题。

![](img/f3a733a5511e8c4e875016cff785a4e0.png)

![](img/e86f6fccd20c9fb510883ce2315f58dd.png)

1.  如何找到产品的 PMF

# 1\. 什么是PMF？

增长最核心的是找到产品的 PMF（Product-Market Fit，产品-市场契合）

# 2\. 怎么判断你找到了 PMF？

用户不用推广就自己来，而且越来越多 (活跃用户持续增长)。

用户用完还会再来 (留存率高)。

用户会主动推荐给朋友 (口碑传播，NPS 净推荐值高)。

用户愿意为你的产品花钱 (付费转化率高)。

# 3\. 找到 PMF 的四步路径：

第一步：聚焦“目标用户 + 痛点”

想清楚你的产品是为谁解决什么问题的？需求是刚需还是伪需求？是高频还是低频？

我们创业，最好选择“刚需非高频”或“刚需高频”的领域。

第二步：构建 MVP 进行验证

不要一开始就想做个大而全的产品。聚焦核心痛点，用最快的速度推出一个最简陋的版本去测试市场。

第三步：观察用户行为，快速迭代

通过前面提到的数据分析工具，观察用户是否会留存？是否会频繁使用某个核心功能？他们是否愿意付费？根据这些数据，快速迭代你的产品。

第四步：打磨价值主张，扩大传播

当你在一个小范围的用户群体中验证了 PMF 后，就可以提炼出你产品的独特价值主张 (UVP)，然后通过内容、广告等方式，把你的产品推广给更多的人。

1.  运营增长

1.  冷启动阶段（0 → 1）

目标：解决“没人知道、没人用”的问题，找到早期种子用户并形成初始口碑。

常见方式：

.

精准种子用户获取

从创始人/团队的关系网切入（朋友、行业资源、社区）。

找到目标用户聚集地（微信群、Reddit、Discord、论坛、细分行业社群）。

通过邀测/内测身份营造稀缺感。

.

价值驱动传播

提供对某类用户极具差异化的核心价值（“10 倍体验”）。

举办“首批体验官”“测试者”招募活动，用户有荣誉感。

.

低成本内容曝光

发布产品故事、开发日志、对比竞品的痛点解决方案。

在小范围的垂直社区持续分享（比如 indiehackers、掘金、知乎、X/Twitter）。

.

激励机制

早期推荐奖励（推荐 1 人送 Pro 月卡、周边）。

内测用户反馈奖励（送权益）。

这几个都是比较常用的方式，也是成本比较低的方式，如果你只是想快速验证 MVP，可以通过广告投放的方式，

我们产品在冷启动阶段，

一是通过社媒营销在 B 站等平台发布内容，

二是在一些社群分享优质内容，找到了第一批比较精准的种子用户，初步验证了假设。

因为我们产品确实是可以给用户提供价值的，所以慢慢也就形成了口碑传播。

![](img/fba43396ae4fafb02f75b17e6bb1ce30.png)

![](img/08960815053ccac76f9e4a87d0f8c6f5.png)

![](img/e3dc20318f6a1b7c299cb9709d9a93ab.png)

1.  增长加速阶段（1 → 10）

目标：让产品形成稳定增长曲线，验证留存与转化。

常见方式：

1.增长黑客方法

A/B 测试核心转化流程（注册 → 使用 → 付费）。

分析用户行为数据，优化留存。

2.口碑与裂变

引入邀请机制（推荐返利、团队协作必须邀请）。

制造社交货币（分享成果、展示身份）。

3.内容与 SEO

持续产出和产品相关的内容（教程、案例、对比）。

做 SEO/ASO，让用户主动搜到。

4.场景化合作

与相关工具/服务做跨界联合（比如 Zapier 集成）。

垂直行业达人测评，借力外部流量。

这个阶段就需要通过专业的增长黑客方法，

就是我们前面强的一些数据统计和分析的方法，逐步通过数据分析来指导优化产品，

我们也是通过数据分析快速迭代优化产品，我们很多用户的反馈也都是说我们能快速响应用户需求，更新很快。

1.  规模化扩张阶段（10 → 100）

目标：跑通可持续增长模式，实现大规模获客与营收。

常见方式：

1.品牌与市场营销

做品牌定位与差异化宣传。

广告投放（Google Ads、Facebook Ads、抖音/快手）。

2.渠道与生态

入驻平台市场（App Store、Chrome 插件、SaaS Marketplace）。

开放 API/插件，形成开发者生态。

3.增长飞轮

用户创造内容（UGC）、用户分享成果 → 吸引新用户。

付费收入 → 再投放广告 → 获客。

数据驱动持续优化 → 提高转化与留存。

4.国际化/多市场扩张

本地化（语言、支付方式、文化适配）。

分渠道运营（国内用抖音/小红书，海外用 Reddit/HN/Product Hunt）。

我们通过 1-10 的阶段已经跑出了增长模型，这个阶段就可以放大了，

这个阶段广告投放可能就需要成为主要的增长渠道了，然后可以尝试做品牌建设，

品牌是可以给你带来流量和溢价能力的，比如苹果、特斯拉品牌可以自传播和实现品牌溢价。

1.  核心思路总结

冷启动靠精准：找到最痛的用户，提供极致价值。

增长靠裂变：让用户替你带用户。

规模化靠体系：品牌、渠道、生态，形成可持续增长飞轮。

# 08 持续迭代优化产品

开发产品切记完美主义，不要搞。我们要采用敏捷开发模式，就是要边走边看，快速试错，持续迭代。

咱们独立开发者或者小团队的优势就是可以快速调整方向，所谓船小好调头，不像大公司，

他们一旦决定要开发一个产品，就会投入大量资源，不会轻易改变决策。

产品要想持续迭代优化，其核心是 建立“用户反馈—数据分析—产品迭代—验证”闭环，

并在不同阶段有不同的重点，下面我给你拆解成一个可操作的体系：

1.  建立反馈机制

1.1 用户直观反馈

应用内反馈入口（“意见反馈”按钮）。

用户调研问卷、NPS（净推荐值）调查。

客服、社群收集用户意见。

1.2 行为数据反馈

事件埋点：点击、停留、转化路径。

使用时长、留存率、功能使用频率。

热力图/录屏（比如 Hotjar）观察交互痛点。

前面讲过的很多方法，比如在网站右下角增加反馈收集表单

![](img/68b7bf6a070ecb7e1a3e360cda34b454.png)

![](img/dde21bef62db33d22a968fc909c2550f.png)

或者增加 AI 客服

![](img/8648b3b6ec29bb3ebe62571a3cf5816c.png)

1.  数据驱动决策

2.1 分析关键指标（AARRR 模型）

Acquisition（获客）：新用户来源。

Activation（激活）：是否顺利完成首次关键操作。

Retention（留存）：多少用户会回来。

Revenue（收入）：转化率、客单价。

Referral（推荐）：用户是否自发推荐。

2.2 问题定位

如果留存差 → 说明产品价值不足。

如果转化差 → 说明收费模式或价值传达有问题。

如果增长停滞 → 说明推荐/分享机制不够强。

通过数据统计工具，前面也有讲过，来持续分析优化产品指标

![](img/547e70981f229457a3dc41622c9ae243.png)

1.  迭代优化方法

3.1MVP 验证

在新功能上线前，先用低成本验证（原型、灰度测试、小范围内测）。

不追求完整，而是快速验证用户是否需要。

3.2 小步快跑、持续试错

每次迭代聚焦一个核心目标（如提高留存、优化转化）。

每 1～2 周上线小版本，验证效果。

3.3 灰度发布 & A/B 测试

部分用户先体验，避免全量风险。

同时测试多个版本，数据说话。

快速迭代这个很重要，我们通常是自己先 YY 出一些想法，这些想法很可能都是错误的，所以需要快速上线验证，

如果有问题可以及时修改，建议产品迭代 1-2 周一个版本，我们产品目前已经迭代了 30 多个版本

1.  形成增长飞轮

4.1 用户共创

邀请种子用户参与功能设计（“功能投票池”）。

社区共建，用户产出案例、模版、脚本。

4.2 数据驱动的持续优化

每个版本发布后，都要对比关键指标的变化。

保留有效改动，淘汰无效尝试。

4.3 迭代节奏

初期：快速试错，2 周迭代。

成长期：稳定迭代，月度版本。

成熟期：大版本规划，季度发布。

经过这些手段和方式你大概可以构建出自己产品的价值网络，这将形成你产品的增长飞轮，你需要做的就是不断优化这个飞轮的增长效率。

1.  总结成一句话

用户声音是方向盘，

数据指标是仪表盘，

MVP 和 A/B 测试是实验室，

产品迭代是引擎。

这样才能保证产品持续优化，不断提升用户体验和商业价值。

1.  产品开发与实现

# 1\. 本章概要

本章概要：

本章将聚焦于一个“快速开发 AI 产品”的实战案例，手把手教你如何复刻一个拥有百万流量的 AI 工具站。

我们会从产品的选择、需求分析开始，接着设计技术方案，

并逐步实现后端接口和前端 UI。内容涵盖框架安装、页面开发、联调测试，

直到项目发布上线、用户登录、域名绑定、SEO 优化及数据监控的全流程。

# 本章航线图

完成本章节的学习和实操，即可完成航线图的：

第四阶段：百万流量站复刻（约 4 天）

1.  产品实现：从需求到技术、前后端开发与 UI 实现（约 2 天）。

1.  项目部署：完成联调、发布、用户管理、域名绑定与 SEO 优化（约 2 天）。

教学视频请点击下方链接，进入飞书文档查看⬇️

AI工具站-教学视频

在刷 Toolify 榜单时，我发现一个近期排名快速增长的网站：https://imageprompt.org/。

它是一个图片提示词（Prompt）优化工具，实现起来不算复杂，但月访问量高达一百多万。

这非常适合作为我们从 0 到 1 复刻一个 AI 工具站的实战案例。

![](img/93358506c90ab608c4f8c41181167ecc.png)

![](img/a2fe4106f830bf513d7d7871edecbd0a.png)

# 2\. 需求分析

首先我们来分析一下需求，

图片提示词反推，这是网站的核心功能。上传一张图片，它能反推出适用于 Midjourney, Stable Diffusion 等不同模型的提示词。

![](img/f18c4478dc4e7017b277bd157baca3ff.png)

图片上传支持本地上传和 URL 上传

![](img/2a317737dbf99af7604569a421f076e2.png)

有一个提示词的多语言翻译

有一个提示词优化的功能，就是把用户输入的自然语言格式化成 AI 模型能识别的语法

![](img/3fb14887e6fcf4fe11b2a624d3eb07eb.png)

还有其他功能：文生图、图生图、视频提示词反推、图片生成视频等

![](img/ff07adbfe3b763302af22f15864ea825.png)

我们因为时间有限，就只做核心功能，提示词反推

# 3\. 技术方案设计

# 3.1 技术分析：

我们来分析一下技术方案该如何实现，主要是 4 种提示词的返回实现

1.  General Image Prompt，通用提示词生成，这个我们就用多模型大模型的视觉理解功能就可以实现，直接把图片给到大模型，让它直接生成一个自然语言描述，这里我们用豆包 Doubao-Seed-1.6-vision 来实现。

2\. Flux: Fluex 有对应的提示词反推插件 PromptGenV2

1.  Midjourney： 有提示词反推功能

1.  Stable Diffusion：上面说过了 有提示词反推插件 WD14 Tagger

# 3.2 方案设计

我们如何实现这个功能呢？

方案一（自己部署模型）：为 Midjourney, Stable Diffusion 等分别部署专用的提示词反推模型。这个方案效果最好，但成本极高，每个模型都需要一台 GPU 服务器，每月成本至少几千块，不适合我们。

方案二（寻找 API）：找现成的提示词反推 API。但我找了一圈，发现这类 API 非常少，大多是文生图的 API。

方案三（折中方案，我们的选择）：

.

使用一个通用的多模态大模型（比如豆包 Doubao-Seed-1.6-vision）先对图片进行理解，生成一段自然的语言描述。

.

再用另一个大模型，结合我们提供的提示词模板和语法规则（通过知识库），将这段自然语言描述“翻译”成适用于 Midjourney, Stable Diffusion 等不同模型的专业提示词。

这个方案成本最低，实现最快。后端 API 我们可以直接用“扣子 (Coze)” 的工作流来实现，这样我们只需要专注于前端页面的开发。

我们来画一下业务流程图：

![](img/9bbf32ae4d43119d3ef8f8e3321bd625.png)

然后 服务端 API 打算用扣子工作流实现，因为扣子可以调用大模型和知识库，而且还提供知识库，那么我们项目中指需要实现页面交互就可以了。

1.  后端接口实现

# 4.1 扣子工作流搭建

.

打开扣子主页 https://www.coze.cn/home ， 直接创建一个工作流，工作流也可以通过 API 调用

.

名字就叫 imagePromptAPI，可以根据用户输入的图片和选择的不同模型来生成对应的提示词

这个工作流中我们需要添加 4 个大模型节点分别对应 4 种提示词的生成，

1 个选择器用来控制根据用户选择的提示词类型选择不同的大模型，

1 个变量聚合节点，聚合 4 个模型的输出结果。

.

我们需要去找 3 个模型对应的提示词风格的一些实例，这些实例提示词需要放到知识库给大模型调用，比如找 Stable Diffusion 的提示词，直接 Google 搜索关键词：

![](img/da597ef7fc9c585e423cc136438d2b37.png)

.

不同模型的提示词结构不太一样，比如 SD 的提示词结构是 （质量）+风格+主体+细节+其它 ，

然后还有权重符号 （）和[]符号 等。那么对应的 SD 提示格式化完整的 Prompt 可以这样写：

```
Stable Diffusion prompt 助理

你来充当一位有艺术气息的Stable Diffusion prompt 助理。

## 任务

我用自然语言告诉你要生成的prompt的主题，你的任务是根据这个主题想象一幅完整的画面，然后转化成一份详细的、高质量的prompt，让Stable Diffusion可以生成高质量的图像。

## 背景介绍

Stable Diffusion是一款利用深度学习的文生图模型，支持通过使用 prompt 来产生新的图像，描述要包含或省略的元素。

## prompt 概念

- prompt 用来描述图像，由普通常见的单词构成，使用英文半角","做为分隔符。
- 以","分隔的每个单词或词组称为 tag。所以prompt和negative prompt是由系列由","分隔的tag组成的。

## () 和 [] 语法

调整关键字强度的等效方法是使用 () 和 []。 (keyword) 将tag的强度增加 1.1 倍，与 (keyword:1.1) 相同，最多可加三层。 [keyword] 将强度降低 0.9 倍，与 (keyword:0.9) 相同。

## Prompt 格式要求

下面我将说明 prompt 的生成步骤，这里的 prompt 可用于描述人物、风景、物体或抽象数字艺术图画。你可以根据需要添加合理的、但不少于5处的画面细节。

### 1\. prompt 要求

- 你输出的 Stable Diffusion prompt 以“**Prompt:**”开头。
- prompt 内容包含画面主体、材质、附加细节、图像质量、艺术风格、色彩色调、灯光等部分，但你输出的 prompt 不能分段，例如类似"medium:"这样的分段描述是不需要的，也不能包含":"和"."。
- 画面主体：不简短的英文描述画面主体, 如 A girl in a garden，主体细节概括（主体可以是人、事、物、景）画面核心内容。这部分根据我每次给你的主题来生成。你可以添加更多主题相关的合理的细节。
- 对于人物主题，你必须描述人物的眼睛、鼻子、嘴唇，例如'beautiful detailed eyes,beautiful detailed lips,extremely detailed eyes and face,longeyelashes'，以免Stable Diffusion随机生成变形的面部五官，这点非常重要。你还可以描述人物的外表、情绪、衣服、姿势、视角、动作、背景等。人物属性中，1girl表示一个女孩，2girls表示两个女孩。
- 材质：用来制作艺术品的材料。 例如：插图、油画、3D 渲染和摄影。 Medium 有很强的效果，因为一个关键字就可以极大地改变风格。
- 附加细节：画面场景细节，或人物细节，描述画面细节内容，让图像看起来更充实和合理。这部分是可选的，要注意画面的整体和谐，不能与主题冲突。
- 图像质量：这部分内容开头永远要加上“(best quality,4k,8k,highres,masterpiece:1.2),ultra-detailed,(realistic,photorealistic,photo-realistic:1.37)”， 这是高质量的标志。其它常用的提高质量的tag还有，你可以根据主题的需求添加：HDR,UHD,studio lighting,ultra-fine painting,sharp focus,physically-based rendering,extreme detail description,professional,vivid colors,bokeh。
- 艺术风格：这部分描述图像的风格。加入恰当的艺术风格，能提升生成的图像效果。常用的艺术风格例如：portraits,landscape,horror,anime,sci-fi,photography,concept artists等。
- 色彩色调：颜色，通过添加颜色来控制画面的整体颜色。
- 灯光：整体画面的光线效果。

### 2\. 限制：
- tag 内容用英语单词或短语来描述，并不局限于我给你的单词。注意只能包含关键词或词组。
- 注意不要输出句子，不要有任何解释。
- tag数量限制40个以内，单词数量限制在60个以内。
- tag不要带引号("")。
- 使用英文半角","做分隔符。
- tag 按重要性从高到低的顺序排列。
- 我给你的主题可能是用中文描述，你给出的prompt和negative prompt只用英文。
```

同理，其他模型对应的提示词：

```
Flux Prompt 助理
你来充当一位有艺术气息的 Flux Prompt 助理。

## 任务

我用自然语言告诉你要生成的主题，你的任务是根据主题想象一幅完整的画面，然后转化成一份详细的、高质量的 Flux Prompt，让 Flux 可以生成高质量的图像。

## Prompt 概念

Flux 的 Prompt 更接近自然语言，语法结构比 Stable Diffusion 更自由。它常常由几个用竖线 “|” 分隔的部分组成，每个部分包含画面描述的不同维度。

## Prompt 格式要求

Flux 的 Prompt 输出时，需包含以下部分（从左到右，按重要性排列）：

主体 (Subject)
画面的核心内容，用英文详细描述（人、物体、场景、抽象概念等）。
如果是人物，必须包含面部细节（eyes, lips, nose, eyelashes, expression 等）。

风格 (Style/Medium)
图像的艺术形式或媒介，例如：photography, oil painting, digital art, anime, 3D render, concept art。

画质与细节 (Quality & Details)
永远包含高质量标签：best quality, ultra-detailed, 8k, masterpiece。
可以加入 HDR, sharp focus, cinematic composition, professional, extreme detail 等词。

光影与氛围 (Lighting & Atmosphere)
描述画面的光影和氛围，例如：soft sunlight, cinematic lighting, moody atmosphere, dramatic shadows, studio lighting。

色彩 (Color Palette)
描述整体色调，例如：vivid warm colors, pastel tones, monochrome, cyberpunk neon, golden hour。

附加修饰 (Extra Elements)
用来补充画面的独特感，如 dreamy, futuristic, surreal, elegant, romantic atmosphere。

## 限制
只用英文单词或短语，不要整句。
使用竖线 “|” 分隔各部分。
单词数量不超过 60 个。
Tag 按重要性从左到右排序。
只输出 Flux Prompt，不要解释。

✅ 示例
输入主题：少女在玫瑰花园里微笑
输出 Flux Prompt：
A beautiful young girl standing in a rose garden, detailed eyes, lips, nose, long eyelashes, soft smile | hyper-realistic photography | best quality, ultra-detailed, 8k, masterpiece, cinematic composition | soft sunlight, HDR, dreamy atmosphere | vivid warm colors, golden hour tones | elegant, romantic mood
```

Midjouney 提示词：

```
Midjourney Prompt 助理
你来充当一位具有艺术敏感度的 Midjourney Prompt 助理。

## 任务
我用中文告诉你一个主题，你的任务是根据这个主题构想完整画面，然后生成一份高质量的 Midjourney Prompt，可以直接用于 Discord 的 /imagine 命令。
Prompt 语法结构要求

使用 /imagine 作为开头，后跟 prompt 文本。
Prompt 包含以下主要部分（尽量简洁且丰富）：

主体 (Subject)：画面核心内容，用英文详细描述（人、物、景或抽象概念）。
若为人物，务必包含面部特征，如 eyes、lips、nose、expression 等。

媒介/风格 (Medium / Style)：例如 photography, oil painting, digital art, illustration, concept art 等。
环境 (Environment)：场景或背景，包括地点、氛围、时间等。
光影 (Lighting)：例如 golden hour、soft lighting、cinematic lighting 等。
构图 (Composition)：视角，如 close-up, aerial view, wide angle, portrait 等。
色彩与氛围 (Color & Mood)：如 vibrant colors, moody tones, pastel, romantic 等。
参数 (Parameters)：加在结尾，控制 aspect ratio、stylize、chaos、style、weird 等（如 --ar 16:9 --stylize 750 --v 6）。

## 推荐结构示例：
/imagine 主体, 媒介风格, 环境, 光影, 构图, 色彩氛围 --ar 宽高比 --stylize 数值 --v 版本号
可以使用 多重提示权重（multi-prompting） 通过 :: 语法调整关键词重要性（可选）。例如：
subject::2 environment::1 mood::0.5

## 限制
不要出现中文，prompt 必须是英文。
不要包含解释性文字，仅输出一行完整的 prompt。
保持词语简洁明了，不要超过 60 个词左右。
避免否定描述，若需排除元素请使用 --no 参数，例如 --no text, --no watermark。

## 示例
输入主题（中文）：
 “夕阳下海边戴草帽的少女微笑着看向远方”
输出 Midjourney Prompt：
/imagine a smiling young woman wearing a straw hat on the beach at sunset, digital painting, soft golden light, wide angle, warm pastel colors, serene romantic mood --ar 16:9 --stylize 750 --v 6
```

我们定义的 API 的输入数据结构是

```
{
    "userQuery": "请描述一下这个图片",
    "img"： 图片二进制数据,
    "promptType": "" // 提示词类型 "midjouney" || "stableDiffusion" || "flux" || "normal"
}
```

所以开始节点要这样设置，以对应输入的数据结构

![](img/18eec3607e1b705c3c36122edb22f918.png)

第二个节点就是图片理解

我们需要先用豆包 1.6 进行图片理解，生成自然语言提示词，这个节点的用户提示词是：

![](img/82746a7b6085214aa389cd2de3a2de70.png)

```
## 图片描述助手
你是一个图片描述助手，可以理解用户提供的图片，并用自然语言描述出来

## 技能

用自然语言描述图片画面，并用模型能理解的语言描述，需要提供AI绘画模型能理解的语言描述

## 工作流

根据用户输入的图片{{img}} 和 需求{{userQuery}}进行图片处理任务
```

第三个节点是选择器

根据条件匹配不同的模型，相当于代码中的 if else

后面 3 个节点就是对应的其他 3 个类型的大模型生成节点了，提示词前面有写，

模型的话可以选 deepSeek-V3.1 速度和效果都比较好

下面一个节点就是变量聚合，用来合并前面 4 个模型的输出结果，统一到一个变量输出

![](img/9d3dcfcf00748265dc082a1b1719234b.png)

最后结束节点返回聚合的结果

![](img/f05273e79eb29cdc0a520e369d7afbdd.png)

工作流试运行成功就可以发布了

![](img/8ca1e091ff08c6ffb0c99bd9d6028380.png)

# 4.2 API 配置

调用扣子 API 之前我们需要先生成一个个人访问令牌，后面加到配置文件

1.  前端 UI 实现

TIPS: 过程中如果遇到任何问题，可以直接告诉 Claude Code ，让它解决

![](img/1296d2ce0cab43a6dcf65e07ac52e814.png)

![](img/7f5ab1017fc9f454b7cd27728081bdea.png)

# 5.1 SassFly 框架介绍

我们将使用一个名为 Saasfly 的开源 Next.js 框架。它已经为我们集成了登录鉴权、用户管理、数据库、多语言、支付等 SaaS 产品的常用基础功能，让我们能专注于核心业务开发。

# 5.2 Frameworks

Next.js - The React Framework for the Web (with App Directory)

NextAuth.js - Authentication for Next.js

Kysely - The type-safe SQL query builder for TypeScript

Prisma - Next-generation ORM for Node.js and TypeScript, used as a schema management tool

React-email - A React renderer for creating beautiful emails using React components

# 5.3 Platforms

Clerk - The most comprehensive User Management Platform

Vercel – Deploy your Next.js app with ease

Stripe – Payment processing for internet businesses

Resend – Email marketing platform for developers

![](img/661d28fcd4208e8d8c6fcd5b8ca198e2.png)

而且这个是开源的框架，我们可以免费使用

# 6\. 框架安装和初始化

# 6.1 克隆源码

前面我们已经安装好了 git， 直接打开 Saasfly Github 仓库，复制克隆地址

![](img/98c493ba3ce8f5d8bf7bb436d5ebd6bb.png)

在终端执行命令：

```
git clone https://github.com/nextify-limited/saasfly.git
```

![](img/e6f554e30621d4284036279ef4c0f7ee.png)

# 6.2 Claude Code 初始化

然后用 Trae 打开项目目录

![](img/3d96b677e79c335aeb531f9b972f93ef.png)

再开一个终端，打开 CC，然后执行 /init 进行项目初始化，会生成一个 CLAUDE.md 关于项目介绍的文档

![](img/163e1664448e7d818e87cee0a0386786.png)

这个文档说明了项目使用的技术栈、主要功能和启动方式等

然后我们也可以在里面定义一些自己的编码规范等

# 6.3 传到 Github 仓库

我们需要把项目代码上传到自己的代码仓库，先在 Github 创建一个仓库

然后修改当前项目的 remote url， 改成你新仓库的地址

```
git remote set-url origin git@github.com:fuyunzhishang/imagePrompt.git
```

执行一下 git push 把本地代码推送到远程仓库

![](img/05cc6550e58cd0b957b8d9a58c6e13b8.png)

刷新 Github 页面就可以看到代码了

![](img/38406fd651179ab9099430cf1a801072.png)

# 6.4 项目同步到 Vercel

在 Vercel 中创建新项目

![](img/4352085e0b9cc6c086d959836ca3dc5f.png)

导入我们刚创建的 Github 项目

Framework 改成 Next.js

![](img/7fb917025733f5f27ab60cafbe09ab74.png)

1.  复刻 UI

# 7.1 项目配置和启动

我们先把项目的依赖安装一下， 然后本地运行起来

官方文档有具体步骤：https://docs.saasfly.io/zh-cn/get-started/manual-setup/

Saasfly 推荐用 Bun 代替 npm，需要先按照一下 bun

为了更好的体验，请使用 Bun （How to install Bun） 来代替 npm 或者 yarn。

通过 npm 安装 bun

```
npm install -g bun # the last `npm` command you'll ever need
```

然后通过 bun 安装项目依赖

```
bun i
```

生成 Prisma Types

请确保在 saasfly 文件夹下，然后使用 bun 生成 Prisma types：

```
cd packages/db/
bun db:generate
```

输出结果：

```
✔ Generated Kysely types(1.7.1) to./ prisma in 1.32s
```

设置环境变量

进入 saasfly 文件夹， 复制 .env.example 文件，并将复制出来的新文件重命名为 .env.local，然后进入文件写入你的环境变量。

```
cd saasfly
cp .env.example .env.local
```

请确保您有一个可使用的 Postgres DB （如果您还没有 Postgres，请点击这里） 并且已创建了一个数据库。

如果已经创建过 Postgres 数据库可以直接在环境变量修改，或者可以在 Supabase 中创建一个新数据库

![](img/62c16e115888222cf843cdd29106eaed.png)

然后查看刚创建数据库的密码等信息，设置到 env.local 的环境变量中

![](img/073f618f61719e456a9a2c965c32ff18.png)

![](img/81f560675c55edcf2c98d87d5a154474.png)

注意要选下面的链接方式，直接链接不支持 IPV4

POSTGRES_URL 必须要在 .env.local 文件中定义：

```
# 格式例子：
# POSTGRES_URL="postgres://{USER}:{PASSWORD}@{DB_HOST}:{DB_PORT}/{DATABASE}"

POSTGRES_URL="postgres://postgres:123456@127.0.0.1:5432/saasfly"
```

![](img/178810344f641d6bd6a5cf5ea9175bfb.png)

然后，使用 bun 去创建数据库表（tables）：

```
bun db:push
```

输出结果：

![](img/5730f963a9e79f3bc5fc93464eaaf04d.png)

然后再 supabse 中查看，已经有数据表了

![](img/b42419cf72f07c79b4cd3d2f3bc2d7b3.png)

启动本地 web 服务

```
# 注意要先切换到项目根目录
cd ..
bun run dev:web
```

![](img/2fb7cc61d35438e21ef18b05a8534741.png)

可以看到项目已经运行在本地 3000 端口

但是现在我们直接打开显示 404，让 CC 排查一下问题，以后遇到所有问题都可以让 CC 去解决

![](img/986de045b32b7103039250357cb9d3a9.png)

这个问题是 Saasfly 默认使用 clerk 鉴权，现在没有配置所以报错，clerk 需要注册账号配置啥的，我觉得太麻烦，直接让 CC 改成 NextAuth 鉴权

![](img/d939ea42432174df057ccfc89fbd83b8.png)

```
 把鉴权改成NextAtuh    
```

![](img/06ec5b8bdd223914ca04eb30d680674b.png)

等个几分钟，CC 就改完了

![](img/fe9ffcae3de071af6c1be10ec4138de5.png)

如果有错误，直接把错误复制给 CC，让它继续改，改到没问题为止

![](img/6c112cb42de52dbc3b110ec2b522795a.png)

成功运行之后，我们会看到 Saasfly 的默认界面

![](img/eaaa963341a7a1c6902484d2a2942fad.png)

接下来我们来提交一下代码，要小步提交，避免代码丢失

推送到远程仓库

![](img/9abe491cefbae4617c41365d80db9096.png)

# 7.2 前端页面开发

# 7.2.1 落地页开发

落地页是我们网站流量承接的一个页面，主要展示和介绍网站的功能，并链接到二级功能页面，这里我们就直接模仿对标网站。

然后让 CC 复刻这个页面，实现我们自己的登录页

```
复刻这个页面，实现落地页面，完成后要测试没有报错
```

![](img/7963fcc2bba6a9b7f395cbc918f4806b.png)

几分钟 CC 完成了任务

![](img/437592b0673a927347bd1eb273fd5963.png)

如果遇到问题，继续让 CC 修复

CC 修改很难一步到位，可能需要一点点修改，我们就根据修改结果，指导 CC 逐步优化

比如现在页面样式虽然改了，但是文案还没改，就继续修改

![](img/bb26bea0618b5cdb6e839055efaccd05.png)

现在这个页面有点像了，我们先实现主要功能，后面再优化细节

# 7.2.2 功能页开发

落地页开发好，然后我们来开发功能页面

![](img/70c1ad2b29ad043107a92e1ad67012dd.png)

```
根据这个页面截图，进行功能页面的开发，并在落地页加上链接导航
```

# 7.2.3 细节优化

CC 生成会有很多细节问题，比如多语言硬编码、各种样式问题等，所以我们需要针对这些细节让 CC 持续优化

1.  项目部署与后期运营

# 1\. 联调、测试并发布

让 CC 实现前端页面调用后端扣子的 API，扣子支持 API 调用工作流，这是官方文档 https://www.coze.cn/open/docs/developer_guides/workflow_run，我们直接给 CC 研究，让它实现相关功能。

```
实现一下image to prompat 的功能，需要调用扣子工作流来实现图片的提示词生成，步骤如下：
1\. 调用文件上传接口实现图片上传 这是接口文档 https://www.coze.cn/open/docs/developer_guides/upload_files
2\. 然后通过工作流API调用提示生成功能 生成API，这是接口文档 https://www.coze.cn/open/docs/developer_guides/workflow_run
3\. 接口鉴权的token 和workflow_id 配置到配置文件中
```

功能基本完成了

然后发布到 Vercel

我们需要在 Vercel 创建一个项目，仓库关联到我们在 Github 创建的仓库

![](img/891989bf4e4cab320ab61473ea6e287c.png)

如果遇到部署问题，让 CC 解决，直到部署成功，因为环境差异的问题，可能在本地是可以编译成功，但是部署失败是正常的

部署了几十次终于成功了

![](img/43d0126d3960f1f2a02630dcbef52855.png)

我们来访问一下

![](img/eefce5dff74eb533ef5664a10783ea56.png)

部署好的网站，vercel 会给一个默认的域名

1.  用户登录

我们修改一下默认的登录页面样式，然后接入 google 登录

![](img/61f80624db1bf0b378798ca359040f1a.png)

```
1\. 优化登录页样式，去掉saasfly的文案，改成imagePrompt
2\. 去掉github登录
3\. 实现google登录
```

CC 改好之后，我们只需要配置 Google ID 和 SECRET 就可以了

Google 登录凭证需要申请，进入 Google Cloud ， 点击 APIs & Services

然后选择左侧的凭证

![](img/099052dc1a336e0114f68dc056453514.png)

然后创建一个凭据

![](img/91404c48531e1a68d363644c23f1d553.png)

选 OAuth 客户端 ID

应用类型选 web 应用，授权和回调 url 就填 http://localhost:3000，现在是本地开发，就填这个本地地址，等发布线上需要填线上域名

等 5 分钟，再测试登录页面登录

如果遇到登录问题，我们把错误详情给 CC 解决

![](img/065093b5990d6d4274e6a3a89c6da864.png)

我遇到的问题是回调地址填的不对，应该是 http://localhost:3000/api/auth/callback/google

修改之后就可以正常登录了

![](img/13821d94f99458013b40c272c4f5de2a.png)

![](img/96d5e0d3be30a89f6534b59eb7989061.png)

然后我们就可以在 supabase 后台看到登录的用户信息了

![](img/cc7cf0845cb0c93d45b6ae71eaa614b2.png)

1.  域名绑定

线下发布之后，我们需要给网站绑定自己的域名，

域名可以在阿里云、腾讯云、porkbun 等平台注册，注册好之后解析一下就可以了。

Vercel 提供自定义域名服务， 在设置-域名中新加一个域名，然后把解析信息添加到域名提供的 DNS 解析中

![](img/f746d4343ad5341ed781b07d8a6724a1.png)

比如我这里用的 porkbun， 把 vercel 提供的 cname 解析信息复制到域名 DNS 解析

![](img/54be68aefd735003bfb661e2353f86b3.png)

绑定域名之后记得要加到 google 凭证授权 url 中

1.  SEO 优化

然后我们通过 AITDK 来简单分析一下他的关键词，来初步做一下 SEO 的关键词布局

然后我们把这个几个关键词给到 CC，让他在落地页布局这几个关键词

```
对落地页做一下SEO关键词布局，需要围绕着几个关键词进行内容布局：image to prompt, impage to prompt generator, image prompt, prompt generator
```

我们可以看到优化后的关键词布局还比较合理

1.  数据监控

这里我们就用百度的数据监控，首先注册百度统计账号 https://tm.baidu.com/

然后添加一个网站

![](img/7b12c31ec3a32542eb8d3c0abd0b9335.png)

然后获取代码

![](img/b8cb548fbc7ad38f2f857a4fd2344cdc.png)

复制这段代码，添加到网页中

然后给到 CC 就可以了

![](img/d89058bdd80485801e2fc3ab806243d8.png)

1.  常用运维工具入门

1.  服务器管理

宝塔面板介绍：

宝塔面板（BT 面板，全称 宝塔 Linux/Windows 面板）是一款可视化的服务器运维管理工具，主要用于简化服务器的建站、运维和管理工作。它提供了图形化的 Web 管理界面，让用户即使没有太多 Linux/Windows 命令行经验，也能快速上手部署和维护网站、数据库、FTP、SSL 等服务。

![](img/70e9647e9daca1c52f21b7549d40c5a6.png)

1.  主要功能

.

一键环境部署

常见环境：LNMP（Linux + Nginx + MySQL + PHP）、LAMP（Linux + Apache + MySQL + PHP）、Tomcat、Node.js、Java 等。

一键安装、升级、切换不同版本的 Nginx、Apache、PHP、MySQL/MariaDB 等。

.

网站管理

支持快速创建网站、绑定域名、配置 HTTPS（免费 Let's Encrypt 证书）。

提供伪静态规则管理、301/302 重定向、反向代理、负载均衡等功能。

.

数据库管理

支持 MySQL、MariaDB、PostgreSQL、MongoDB。

内置可视化管理工具（phpMyAdmin、Adminer），也支持远程连接。

.

FTP/SFTP 管理

内置 FTP 服务，支持用户分级权限管理。

.

文件管理

Web 界面上传、下载、编辑、解压缩文件。

支持在线编辑代码。

.

安全管理

防火墙管理：端口放行、IP 黑白名单。

系统安全体检，提醒风险配置。

.

计划任务

支持定时备份数据库、网站文件，支持自动清理日志、定时执行脚本。

.

监控功能

服务器 CPU、内存、硬盘、流量等实时监控。

![](img/947eb4ff89470258032699fb5b7e22c5.png)

![](img/6e867addd494a8b4f3b16890d4d0168d.png)

1.  优点

上手简单：对小白和非专业运维人员很友好。

功能全面：建站、运维、管理、监控都能通过一个面板完成。

插件丰富：有应用商店，提供缓存、负载均衡、监控告警、云端备份等插件（部分收费）。

跨平台：同时支持 Linux 和 Windows 系统。

1.  缺点

安全性风险：宝塔本身运行在 8888 端口，如果没做好防护（如修改默认端口、限制 IP、设置强密码），容易被黑客扫描攻击。

性能消耗：相比纯命令行操作，会占用一定的服务器资源。

商业化：基础功能免费，高级插件和一些功能需要付费。

1.  适用场景

个人站长、独立开发者：快速搭建网站（WordPress、Discuz、Shopify 类似系统）。

中小企业：建站、内部系统部署。

学习测试环境：练习 LNMP、LAMP 环境搭建。

1.  安装

具体可参考官方文档 https://www.bt.cn/new/download.html

.

通用安装脚本

```
if [ -f /usr/bin/curl ];then curl -sSO https://download.bt.cn/install/install_panel.sh;else wget -O install_panel.sh https://download.bt.cn/install/install_panel.sh;fi;bash install_panel.sh ed8484bec
```

.

Centos/OpenCloud/Alibaba

```
url=https://download.bt.cn/install/install_panel.sh;if [ -f /usr/bin/curl ];then curl -sSO $url;else wget -O install_panel.sh $url;fi;bash install_panel.sh ed8484bec
```

.

Debian

wget -O install_panel.sh https://download.bt.cn/install/install_panel.sh && bash install_panel.sh ed8484bec

.

Ubuntu/Deepin

```
wget -O install_panel.sh https://download.bt.cn/install/install_panel.sh && sudo bash install_panel.sh ed8484b
```

1.  服务器部署项目

# 1\. 部署方案对比：

部署平台

价格

时间成本

可维护性

自有服务器

16$/月

少

高

Vercel + Supabase

20$ + 25$

配置复杂

中

自己服务器部署就比较简单了，不需要那么多复杂的配置，想安装什么工具都可以，一台服务器可以部署很多个网站，一般的配置2核2G的服务器至少可以部署几十个网站。

这是一个通用部署方案，并不限于某个框架。

# 2\. AI自动部署

AI部署需要比较好用的AI模型， 比如Claude Code，并且适合部署测试环境等，尽量不要让AI操作线上环境，AI操作有风险，操作前请先备份数据或者快照。

服务器用我们前面用过的digitalocean或其他的云计算平台都可以

不过AI发挥没那么稳定，可以需要多试几次。

# 2.1 先要在设置里上传你的公钥

只不过这次要用SSH Key登录，主要因为Windows下面AI不能用密码明文登录服务器

并且需要先上传公钥，在创建服务器的时候选择对应的公钥才会加载

![](img/3714947d45ed3ee68f8d8ac6d02ab12a.png)

# 2.2 创建虚拟机

![](img/6d237bc551ddca6ac4adcbb3ebcced10.png)

# 2.3 然后测试ssh登陆

![](img/787c0a69132700d088286e037467fce0.png)

# 2.4 Claude Code 部署

根据情况给AI明确需求

![](img/04186f01844b9851d4aa31fb8beb4b89.png)

自动部署完成

![](img/897c348f6b2ab1939ed696cbfec61df8.png)

# 3\. 手动部署

.

安装宝塔面板，前面有介绍安装方法

.

安装postgresql数据库，宝塔支持 postgresql环境安装

![](img/45425d08c15c1463e832a3926999f450.png)

创建数据库

![](img/46138b18f723c7798ba7e7b6fad2b56a.png)

.

链接数据库，初始化数据表

默认数据库配置可能没有监听外网ip和权限配置问题导致连接失败，可以让CC去服务器修改

![](img/5d666d44ee2a3a6528df02bd784f7808.png)

![](img/4a1d8247980107ba0eadd2df107844f0.png)

![](img/3610f7c681fae1bf9d62696814270c11.png)

.

数据库同步成功

.

![](img/00b830c4a6c4850f6093e508bc7f5ee3.png)

.

然后测试环境测试你的项目可以运行

.

编译打包项目

![](img/7d3b4b8e19747600be59493927b38aa2.png)

.

然后可能会遇到vercel 的问题，这里我们不用vercel部署，就去掉所有vercel的配置

![](img/9e35e62ee5ac9a0d1d55d10547046aaf.png)

![](img/8ac622982c19500c2ec433b914fd137a.png)

.

服务器安装Node 和Pm2 ，通过宝塔面板安装

![](img/d7fc22bf3fccffd8698f27371f30dcf9.png)

.

进入Node.js版本管理器，更新版本列表，并安装长期版本22.19.0

![](img/ab00f55e90ab401e8f594af34aad8f29.png)

注意要设置命令行版本

.

安装bun, 项目运行需要

.

上传构建产物到服务器，构建好的产物在/saasfly/apps/nextjs目录下，压缩打包

![](img/3560a2af7741ff69d4c1acd01385fdc1.png)

![](img/81d5187572172ea9160e94d299eafece.png)

上传到/www目录下

![](img/c89d35fdd392929da87dac9663442ce3.png)

.

通过pm2 启动，但这个框架因为耦合了很多第三方依赖，需要让AI先剥离有问题的依赖，不然生成环境会报错，遇到错误再让AI修改就可以，需要花费点时间，不然用其他框架也可以。

![](img/ac0a66d7e9fef3261954cfaeb9136dc5.png)

![](img/9d546b64e1f45e945f2717d54286ddb8.png)

# 总结：部署遇到的所有问题和坑，我让AI总结了一个文档

1.  工具站变现进阶

# 1\. 本章概要

本章概要：

本章主要介绍工具站如何实现变现进阶，核心聚焦在产品打造、支付接入、订阅套餐设计以及收款渠道的详细规划与实施。同时，也将深入探讨如何进行流量运营，包括 SEO、社媒营销和付费广告等多种策略，以确保产品获得持续增长。

实战步骤：

产品打造与支付接入

了解国内外支付接入方式的限制与选择

规划产品订阅套餐，包括免费、基础、专业和企业套餐的设计思路与常见结构

深入了解 Stripe 与海外公司注册流程，包括手机号准备、公司注册地选择（英国/美国）、Firstbase 一站式服务及 Mercury 银行优势

Stripe 企业账号开通与 Wise 个人收款及提现

流量运营策略

SEO（搜索引擎优化）：关键词策略、内容建设、权重提升、用户体验优化

社媒营销（SMM）：海外（Twitter/X、Reddit、YouTube Shorts、TikTok、LinkedIn）与国内（小红书、抖音、知乎、微博）常见打法

付费广告（Paid Ads）：Google Ads、Meta Ads、TikTok Ads 等渠道的精准定向、转化追踪和规模化投放

# 本章航线图

完成本章节的学习和实操，即可完成航线图的：

第五阶段：商业化进阶（约 2 天）

1.  产品订阅与收款渠道：规划产品套餐与接入支付方式（约 1 天）。

1.  流量运营策略：深入了解 SEO、社媒营销与付费广告策略（约 1 天）。

# 2\. 接入支付

接入支付目前有几种方式：

国内的个人身份几乎都不支持，至少需要一张香港卡。

.

香港卡个人身份申请，容易封号

.

国外公司，比较稳定

.

国内公司，相对稳定

# 3\. 产品订阅与收款渠道

如果工具站要推出付费订阅，就必须提前规划收款渠道。

常见选择有两类：

个人收款：可以使用 Creem。

企业收款：推荐使用 Stripe，最好通过海外公司名义注册，更加稳定可靠。

这一章主要介绍 Stripe 及相关配套准备工作，其他渠道如 Payoneer、Lemon Squeezy、Paddle 等大家可自行探索。

# 3.1 产品订阅套餐设计

订阅套餐设计其实是 产品商业模式的核心，它既要满足不同用户群体的需求，又要兼顾营收和增长目标。

# 3.3.1 设计思路

1.  分层满足需求

免费用户：降低试用门槛，扩大用户池。

付费用户：享受核心功能、效率提升。

高阶用户：解决专业/企业级需求，附带额外价值（API 调用、团队协作、专属服务）。

1.  价格锚点效应

至少提供 3 个套餐（低、中、高），让用户自然倾向选择中间档位（心理学上的“折中效应”）。

1.  差异化设计维度

使用额度（视频时长、生成次数、存储空间）

功能权限（高级功能、API、批量处理）

服务体验（客服响应速度、团队成员数、白标/定制化）

结算周期（按月/按年，年付打折）

比如我们产品的套餐分成了多个会员等级 ：

![](img/861b39b7851ecacb781465c9092a61ac.png)

# 3.3.2 常见套餐结构

以下以 AI 工具站/视频剪辑 SaaS 为例：

1.  免费套餐（Free）

目标：拉新 & 建立使用习惯

内容：

限制性功能（如导出带水印的视频）

每月有限制的使用额度（如 30 分钟视频处理，100 次 AI 调用）

社区支持

1.  基础套餐（Starter / Pro）

目标：个人用户或刚起步的创作者

定价：9.9 - 19.9 美元/月

内容：

去除水印

提高额度（如 10 小时视频/月）

常用高级功能（字幕编辑、批量导出、AI 解说）

邮件客服

1.  专业套餐（Advanced / Creator）

目标：重度个人创作者 / 小团队

定价：29 - 49 美元/月

内容：

更高额度（50 小时视频/月）

全功能解锁（API、自动化工作流、跨平台发布）

团队协作（3-5 人）

优先客服（实时聊天支持）

1.  企业套餐（Enterprise / Custom）

目标：中小企业 / 大客户

定价：99 - 299 美元/月（甚至定制报价）

内容：

无限额度或大幅扩容

专属客户经理

白标/二次开发能力

发票 & 法人合规支持

SLA（服务级别协议，保证稳定性）

# 3.2 收款渠道

# 3.2.1 Stripe 与海外公司注册

为什么要注册海外公司？

确保有稳定的收付款渠道与海外银行账户。

许多海外服务对中国大陆身份有限制或风控严格，通过海外公司更容易接入。

海外手机号准备

英国 giffgaff：180 天发一条短信即可保号，费用约 £0.3，官网可免费申请。

美国 Ultra Mobile PayGo：月租约 $3。 以上号码也可以通过淘宝、京东代购。

海外公司注册地选择

英国公司：注册更简单便宜，推荐使用 [1st Formations]，开户可用 Wise 企业账号。

美国公司：更适合拓展业务，常见注册州为 Wyoming（怀俄明州），公司类型 LLC，适合个人开发者。

一站式服务推荐：Firstbase

我选择了 Firstbase，体验更像 SaaS，提供注册、地址公证、EIN、开户一条龙服务。

流程概览：

.

注册公司：选择怀俄明州 LLC。

.

地址公证：租用私人邮箱地址，通过 Notarize 视频公证（1583 Form）。

需准备身份证明（护照/驾照翻译件，淘宝可代办），注意照片与地址要同页展示。

.

EIN 申请：Firstbase 代办，约 10 个工作日收到 IRS 信件。

.

银行开户：推荐 Mercury，关联 EIN、护照后，1 个工作日内审核通过。

完成以上步骤后，你将拥有：公司主体、EIN、私人地址、银行账户、海外手机号。

Mercury 银行的优势

无限量虚拟卡，可按商户限制使用，方便管理订阅与退款。

虚拟卡可绑定支付宝，单笔 200 元以下免 3% 手续费。

可接收账单地址邮件，例如 Google AdSense 验证信件。

支持申请实体银行卡并转寄回国。

Stripe 企业账号开通

使用 EIN 注册即可。

网站语言可切换中文填写信息。

个人验证用护照。

提现账户绑定 Mercury 即可。

建议同时注册 Lemon Squeezy、Paddle 作为备用收款渠道，但需要验证产品网站。

Wise 个人收款与提现

支持大陆身份和护照注册。

入金可通过 Mercury 转账 或淘宝代充。

实体卡（含 3 张虚拟卡）需 $9，支持激活后修改地址再申请。

支持提现至国内银行卡、支付宝、微信，手续费低，汇率优于国内结汇。

👉 推荐进一步了解更稳妥的结汇方式：参考资料

1.  流量运营

其实我的价值观里，产品是第一位的，即你有没有解决用户的问题，所以我们一直抢到需要找到产品的 PMF，即找到产品和市场的匹配度，只要你的产品跟市场足够匹配，那么你就不会缺流量，像特斯拉、微信这种产品就不需要营销，那么话又说回来，咱们新产品开始至少还是需要一部分流量来做冷启动，后续看你产品的发展决定用哪种方式来放大。

# 1\. SEO（搜索引擎优化）

SEO 是最具长期价值的流量来源，核心在于通过优化网站和内容，让搜索引擎更愿意推荐，从而获得免费的自然流量。

关键要点：

1.  关键词策略：聚焦用户真实搜索需求，选择相关度高但竞争不激烈的关键词（工具如 Google Keyword Planner、Ahrefs、Semrush）。

1.  内容建设：持续输出高质量落地页、教程、FAQ、博客文章，解决用户背后的“搜索意图”。

1.  权重提升：通过友情链接、投稿、媒体报道获取高质量外链。

1.  用户体验：优化加载速度、移动端适配、交互设计，让用户停留更久。

适用场景：适合想要长期积累、沉淀品牌价值的产品（如工具站、知识型网站）。

案例：海外的 AI 工具站（如 TAAFT、Futurepedia）依靠 SEO 建立了海量长尾关键词页面，持续获得自然访问。

# 2\. 社媒营销（Social Media Marketing， SMM）

社交媒体是传播最快、最灵活的渠道，核心逻辑是借助平台的传播机制，让用户主动扩散内容。

常见平台：

海外：Twitter/X、Reddit、YouTube Shorts、TikTok、LinkedIn

国内：小红书、抖音、知乎、微博

常见打法：

.

短视频/动图展示：通过对比、演示、教程快速传达产品价值。

.

话题运营：蹭热点、参与讨论，在评论区适度引流。

.

KOL/达人合作：借助影响力人群快速放大传播。

适用场景：特别适合 冷启动阶段，尤其是视觉冲击力强、容易引发讨论的话题型产品。

案例：不少 AI 换脸、AI 绘画应用，都是先在 TikTok 上通过“展示效果视频”走红，之后才实现规模化获客。

# 3\. 付费广告（Paid Ads）

付费广告是最快获得精准用户的方式，能直接用钱买来流量和转化。

常见渠道：

海外：Google Ads（搜索、展示、YouTube）、Meta Ads（Facebook / Instagram）、TikTok Ads

国内：百度推广、抖音广告、快手广告

操作关键点：

.

精准定向：基于兴趣、地域、年龄、消费能力筛选目标人群。

.

转化追踪：使用像素/转化 API 跟踪行为，持续优化投放。

.

小额测试→规模化：先用多组广告小额测试，找到 ROI 最高的素材，再逐步加大预算。

适用场景：适合需要 快速拉新 或 验证市场需求 的产品。

案例：不少 SaaS 创业者会先投放 Google Ads，用“关键词广告 + 免费试用”测试市场接受度，再决定是否长期投入。

# 写在最后

不积跬步，无以至千里。

成长与财富的积累，本质上都依赖复利的力量。复利不是瞬间的改变，而是通过长期坚持，把每一个微不足道的进步，转化为指数级的飞跃。

我们现在所做的事情，就是一种低风险的长期投资。它可能在初期看不到立竿见影的效果，但每一次的学习、实践和微小成果，都会成为你未来爆发的筹码。当风口来临时，你所积累的底层能力和资源，将让你获得远超常人的收益。

所以，真正的差距不是一时拉开的，而是日积月累的复利效应。

现在就开始积累你的复利，把耐心和坚持当作最好的投资工具，让未来的自己感谢今天的你。

最后，期望能看到你的产品，超越下面这条增长曲线。