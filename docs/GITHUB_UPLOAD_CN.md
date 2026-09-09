# GitHub 上传说明（第一次上传）

下面用最简单的网页方式，不需要 Terminal，也不需要 Git 命令。

## 1. 解压文件

下载并解压：

`cosmetic-naming-ai-github-v0.3.zip`

解压后，你会看到：

- SKILL.md
- README.md
- NOTICE.md
- index.html
- intake 文件夹
- docs 文件夹

上传时要上传**这些内容本身**，不要再套一层多余文件夹。

---

## 2. 在 GitHub 新建 Repository

1. 打开 GitHub。
2. 登录账号。
3. 右上角点击 `+`。
4. 选择 `New repository`。
5. Repository name 可以写：

   `cosmetic-naming-ai`

6. Description 可以写：

   `A China-mainland cosmetic product naming AI skill with a no-API interactive brief builder.`

7. 选择：
   - `Public`：任何人都能看到；
   - `Private`：只有你和被授权的人能看到。

8. 先不要勾选自动创建 README，因为包里已经有 README。
9. 点击 `Create repository`。

---

## 3. 上传文件

进入刚刚创建的空 Repository 后：

1. 点击 `uploading an existing file`
   或者：
   `Add file → Upload files`
2. 把解压后的全部文件和文件夹拖进去。
3. 页面下方 `Commit changes`：
   - Commit message 可以写：
     `Initial release v0.3`
4. 点击 `Commit changes`。

上传完成后，仓库首页应该能直接看到 `README.md` 的介绍。

---

## 4. 打开 GitHub Pages

Brief Builder 是静态网页，所以可以免费使用 GitHub Pages 托管。

1. Repository 页面点击 `Settings`。
2. 左侧找到 `Pages`。
3. 在 `Build and deployment` 下：
   - Source 选择 `Deploy from a branch`
   - Branch 选择 `main`
   - Folder 选择 `/ (root)`
4. 点击 `Save`。
5. 等待几分钟。

成功后 GitHub 会显示一个地址，通常类似：

`https://YOUR-USERNAME.github.io/cosmetic-naming-ai/`

打开这个地址后，应该直接进入 Naming Brief Builder。

---

## 5. 把 Builder 地址写进 SKILL.md

当前 `SKILL.md` 里有：

`{{BRIEF_BUILDER_URL}}`

部署 Pages 后：

1. 在 GitHub 打开 `SKILL.md`。
2. 点击右上角铅笔图标 Edit。
3. 搜索：

   `{{BRIEF_BUILDER_URL}}`

4. 替换成你的实际 Pages 地址，例如：

   `https://yourname.github.io/cosmetic-naming-ai/`

5. 点击 `Commit changes`。

这样以后别人拿到 Skill 后，AI 就可以直接告诉用户去哪里打开 Builder。

---

## 6. 自己测试一次

建议按这个顺序：

1. 打开 GitHub Pages。
2. 用 Builder 填一个产品。
3. 点击生成并复制完整 Prompt。
4. 新开一个 ChatGPT 对话。
5. 上传仓库里的 `SKILL.md`。
6. 粘贴 Prompt。
7. 看是否正常输出 6 个候选卡片。
8. 再追问一句：

   `4号不错，但再顺口一点，不要降低创意程度。`

9. 检查新名字：
   - 是否仍然有 rationale；
   - 是否保持 Candidate Card；
   - 是否创意没有突然全部消失；
   - 是否所有新名字仍经过法规语义筛查。

---

## 7. 后面更新版本怎么办？

以后修改 `SKILL.md` 或 Builder：

1. 打开 GitHub 对应文件；
2. Edit；
3. 修改；
4. Commit changes。

GitHub Pages 会自动更新，一般不需要重新部署。

如果一次修改很多文件，也可以重新使用 `Add file → Upload files` 上传覆盖。

---

## 一个小提醒

公开 GitHub 前，建议确认：

- 没有 API Key；
- 没有个人账号密码；
- 没有未公开品牌项目的真实 confidential brief；
- 没有你不想公开的大型市场语料库。

当前这个 v0.3 发布包不需要 API Key。
