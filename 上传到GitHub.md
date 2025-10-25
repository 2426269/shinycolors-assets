# 上传图片资源到 GitHub 指南

## 🚀 快速步骤

### 1. 在 GitHub 上创建仓库

1. 登录 [GitHub](https://github.com)
2. 点击右上角 `+` → `New repository`
3. 填写信息：
   - **Repository name**: `shinycolors-assets` （或其他你喜欢的名字）
   - **Description**: 偶像大师闪耀色彩图片资源
   - **Public** ✓ （必须是公开仓库，jsDelivr 才能访问）
   - **不要**勾选 "Add a README file"
4. 点击 `Create repository`

### 2. 在本地初始化并上传

**打开 PowerShell 或 Git Bash**，然后执行以下命令：

```bash
# 进入资源文件夹
cd "E:\偶像大师\闪耀色彩图片资源"

# 初始化 Git 仓库
git init

# 添加所有文件
git add .

# 创建第一次提交
git commit -m "初始提交：添加偶像大师闪耀色彩图片资源"

# 设置分支名为 main
git branch -M main

# 关联远程仓库（替换为你的用户名）
git remote add origin https://github.com/你的用户名/shinycolors-assets.git

# 推送到 GitHub
git push -u origin main
```

### 3. 验证上传

1. 刷新 GitHub 仓库页面
2. 应该能看到所有文件和文件夹
3. 等待 5-10 分钟让 jsDelivr 同步

## 🔗 使用 CDN 访问

上传成功后，你可以通过以下方式访问图片：

```
https://cdn.jsdelivr.net/gh/你的用户名/shinycolors-assets@main/人物立绘/illumination STARS/樱木真乃/Mano_intial.png
```

**URL 格式：**
```
https://cdn.jsdelivr.net/gh/用户名/仓库名@分支名/文件路径
```

## 📝 在项目中使用

在 `app.vue` 中更新角色数据：

```typescript
const characters = ref([
  {
    id: 1,
    name: '樱木真乃',
    imageUrl: 'https://cdn.jsdelivr.net/gh/你的用户名/shinycolors-assets@main/人物立绘/illumination STARS/樱木真乃/Mano_intial.png',
    images: [
      'https://cdn.jsdelivr.net/gh/你的用户名/shinycolors-assets@main/人物立绘/illumination STARS/樱木真乃/Mano_intial.png',
      'https://cdn.jsdelivr.net/gh/你的用户名/shinycolors-assets@main/人物立绘/illumination STARS/樱木真乃/SCMano.png',
    ],
    // ...其他信息
  },
]);
```

## 🔄 更新资源

当你添加新图片后：

```bash
cd "E:\偶像大师\闪耀色彩图片资源"
git add .
git commit -m "添加新的角色立绘"
git push
```

## ⚠️ 注意事项

1. **仓库必须是 Public**：jsDelivr 只能访问公开仓库
2. **CDN 缓存**：jsDelivr 有 24 小时缓存，更新后可能需要等待
3. **文件大小**：单个文件建议不超过 20MB
4. **仓库大小**：GitHub 免费版建议总大小不超过 1GB
5. **文件名**：避免使用中文和特殊字符，可能导致 URL 编码问题

## 🛠️ 常见问题

### Q: 推送时要求输入用户名密码？
A: GitHub 已不再支持密码认证，需要使用 Personal Access Token：
1. GitHub Settings → Developer settings → Personal access tokens → Generate new token
2. 选择 `repo` 权限
3. 复制 token，在推送时用 token 作为密码

### Q: jsDelivr 无法访问图片？
A: 
1. 确认仓库是 Public
2. 等待 5-10 分钟让 CDN 同步
3. 检查 URL 是否正确

### Q: 如何批量重命名文件（去除中文）？
A: 可以使用 PowerShell 脚本批量处理，需要的话我可以帮你生成




