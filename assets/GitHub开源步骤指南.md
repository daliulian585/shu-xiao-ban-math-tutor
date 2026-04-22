# 数小伴 GitHub 开源步骤指南

## 📋 准备工作

在开始之前，请确保你已经：
- [x] 拥有GitHub账号（如果没有，请访问 https://github.com 注册）
- [x] 本地已安装git（在终端输入 `git --version` 检查）
- [x] 已完成数小伴代码的开发和测试

---

## 🚀 第一步：在GitHub上创建仓库

### 1. 登录GitHub
访问 https://github.com 并登录你的账号

### 2. 创建新仓库
1. 点击右上角的 **"+"** 按钮，选择 **"New repository"**
2. 填写仓库信息：

| 字段 | 填写内容 |
|------|---------|
| **Repository name** | `shu-xiao-ban-math-tutor` |
| **Description** | 数小伴-中职数学教学智能体，基于豆包大模型和Coze平台开发 |
| **Public/Private** | ☑️ Public（公开，便于开源分享） |
| **Initialize with** | ☐ Add a README file（不勾选，我们已经有README了） |
| **.gitignore** | ☐ None（不勾选，我们已经有.gitignore了） |
| **License** | ☑️ MIT License（勾选，自动生成LICENSE文件） |

3. 点击 **"Create repository"** 按钮

### 3. 记录仓库地址
创建成功后，GitHub会显示一个地址，格式类似：
```
https://github.com/your-username/shu-xiao-ban-math-tutor.git
```
**请复制这个地址**，稍后会用到。

---

## 🛠 第二步：配置本地Git仓库

### 1. 查看当前Git状态
在数小伴项目根目录（`/workspace/projects`）执行：

```bash
cd /workspace/projects
git status
```

### 2. 初始化Git仓库（如果还没有）
如果看到 `fatal: not a git repository` 错误，执行：

```bash
git init
```

如果显示 `On branch main`，说明已经是Git仓库了。

### 3. 查看当前分支
```bash
git branch
```

### 4. 切换到main分支（如果需要）
```bash
git checkout main
# 或者
git checkout -b main
```

---

## 📦 第三步：提交本地代码

### 1. 添加所有文件到暂存区
```bash
git add .
```

### 2. 查看暂存的文件
```bash
git status
```

### 3. 提交代码
```bash
git commit -m "feat: 数小伴中职数学教学智能体首次开源"
```

**提交信息规范**：
- `feat:` 新功能
- `fix:` 修复bug
- `docs:` 文档更新
- `style:` 代码格式调整
- `refactor:` 重构代码
- `test:` 测试相关

---

## 🌐 第四步：关联远程仓库

### 1. 添加远程仓库
将第一步中复制的GitHub仓库地址添加为远程仓库：

```bash
git remote add origin https://github.com/your-username/shu-xiao-ban-math-tutor.git
```

**注意**：将 `your-username` 替换成你自己的GitHub用户名。

### 2. 验证远程仓库
```bash
git remote -v
```

应该看到类似输出：
```
origin  https://github.com/your-username/shu-xiao-ban-math-tutor.git (fetch)
origin  https://github.com/your-username/shu-xiao-ban-math-tutor.git (push)
```

---

## ⬆️ 第五步：推送代码到GitHub

### 1. 首次推送（设置上游分支）
```bash
git push -u origin main
```

### 2. 输入GitHub凭据（如果需要）
- **Username**：你的GitHub用户名
- **Password**：不是你的登录密码，而是 **Personal Access Token**

### 3. 创建Personal Access Token（如果需要）
如果使用密码认证失败，需要创建Token：

1. 访问 https://github.com/settings/tokens
2. 点击 **"Generate new token"** → **"Generate new token (classic)"**
3. 填写信息：
   - **Note**: `数小伴开发`
   - **Expiration**: 选择一个过期时间
   - **Scopes**: 勾选 `repo`（所有仓库权限）
4. 点击 **"Generate token"**
5. **复制Token**（只显示一次，请立即复制）
6. 在git push时，用Token代替密码

### 4. 等待推送完成
成功后会看到类似输出：
```
Enumerating objects: 123, done.
Counting objects: 100% (123/123), done.
...
To https://github.com/your-username/shu-xiao-ban-math-tutor.git
 * [new branch]      main -> main
```

---

## 🎉 第六步：验证开源成功

### 1. 访问你的GitHub仓库
打开浏览器，访问：
```
https://github.com/your-username/shu-xiao-ban-math-tutor
```

### 2. 检查文件列表
你应该能看到以下文件：
- ✅ README.md（项目说明）
- ✅ LICENSE（开源协议）
- ✅ src/（源代码目录）
- ✅ config/（配置文件）
- ✅ pyproject.toml（项目配置）
- ✅ requirements.txt（依赖列表）

### 3. 查看README内容
确认README.md的内容显示正常，徽章和链接都能正常工作。

---

## 📝 更新项目信息

### 1. 更新GitHub仓库描述
在仓库主页点击 **⚙️ Settings** → **General** → **About**，填写：
- **Description**: 数小伴-中职数学教学智能体，基于豆包大模型和Coze平台开发
- **Website**: `https://code.coze.cn/web-sdk/7630811434057760804`
- **Topics**: `ai-tutor`, `math-education`, `vocational-education`, `langchain`, `coze`

### 2. 设置仓库可见性
确保仓库是 **Public**（公开）：
- 点击 **⚙️ Settings**
- 向下滚动到 **Danger Zone**
- 确认 **Change visibility** 显示为 **Make private**（如果是Make public，点击它）

### 3. 添加社区健康文件（可选）
在仓库根目录创建以下文件：

#### CODE_OF_CONDUCT.md（行为准则）
```markdown
# 贡献者行为准则

## 我们的承诺

为了营造开放和友好的环境，我们承诺为每位参与者提供友好、安全和无歧视的环境。

## 我们的准则

* 使用友好和包容的语言
* 尊重不同的观点和经验
* 优雅地接受建设性批评
* 专注于对社区最有利的事情
* 对其他社区成员表示同理心

## 不可接受的行为

* 使用性化的语言或图像
* 恶意评论、人身攻击或政治攻击
* 公开或私下骚扰
* 未经许可发布他人的私人信息
* 其他不道德或不专业的行为

## 执行

项目维护者有权删除、编辑或拒绝违反行为准则的评论、提交、代码、wiki编辑和其他贡献。
```

#### CONTRIBUTING.md（贡献指南）
```markdown
# 如何贡献

感谢你考虑为数小伴做出贡献！

## 报告问题

如果你发现了bug或有功能建议，请在 [Issues](https://github.com/your-username/shu-xiao-ban-math-tutor/issues) 中创建。

## 提交代码

1. Fork 本仓库
2. 创建特性分支
3. 提交更改
4. 推送到分支
5. 开启 Pull Request

更多信息请参考 [README.md](README.md)。
```

---

## 📚 添加到案例表格

### 1. 更新案例信息表
在 `数小伴_创AI案例_信息表与报告.md` 中，找到 **相关网址** 字段，更新为：

```markdown
### 相关网址
应用地址：https://code.coze.cn/web-sdk/7630811434057760804
开源仓库：https://github.com/your-username/shu-xiao-ban-math-tutor
```

### 2. 重新生成文档
使用之前的方法重新生成Word和PDF文档。

---

## 🔄 后续维护

### 更新代码
当你修改了本地代码后：

```bash
# 1. 查看修改
git status

# 2. 添加修改的文件
git add .

# 3. 提交修改
git commit -m "feat: 添加新功能"

# 4. 推送到GitHub
git push
```

### 同步GitHub更新（多人协作时）
```bash
# 拉取最新的代码
git pull origin main
```

---

## 🐛 常见问题

### Q1: 推送时提示 "Permission denied"
**A**: 检查以下几点：
- 仓库地址是否正确
- Personal Access Token是否有效
- 仓库权限是否为Public

### Q2: 提示 "fatal: remote origin already exists"
**A**: 远程仓库已经存在，可以使用以下命令更新：
```bash
git remote set-url origin https://github.com/your-username/shu-xiao-ban-math-tutor.git
```

### Q3: 推送时提示 "Updates were rejected"
**A**: 远程仓库有新内容，先拉取：
```bash
git pull origin main --allow-unrelated-histories
git push origin main
```

### Q4: 想要删除仓库
**A**:
1. 访问仓库页面
2. 点击 **⚙️ Settings**
3. 滚动到 **Danger Zone**
4. 点击 **Delete this repository**
5. 按照提示输入仓库名称确认删除

---

## ✅ 完成检查清单

- [ ] 已创建GitHub账号
- [ ] 已创建新仓库（Public + MIT License）
- [ ] 本地代码已提交
- [ ] 已关联远程仓库
- [ ] 已成功推送到GitHub
- [ ] 已验证仓库内容显示正常
- [ ] 已更新仓库描述和标签
- [ ] 已更新案例信息表中的开源仓库地址

---

## 🎯 开源后的好处

1. **比赛加分**：在创AI案例评选中获得"开源分享"指标加分
2. **技术影响力**：展示你的技术能力和开源贡献
3. **社区协作**：吸引其他开发者贡献代码和建议
4. **简历亮点**：丰富你的项目经历和技术栈

---

**恭喜！你的数小伴代码已经成功开源到GitHub了！🎉**
