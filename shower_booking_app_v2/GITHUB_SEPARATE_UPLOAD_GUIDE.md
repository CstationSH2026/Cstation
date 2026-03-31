# GitHub分开上传指南

如果您想将洗浴预约应用上传到GitHub，但又不想覆盖现有的`index.html`文件，本指南将帮助您完成这个操作。

## 方法一：重命名文件后上传

这是最简单的方法，适合大多数用户。

### 步骤1：准备文件

1. 将`shower_booking_app_v2.zip`文件解压到本地文件夹
2. 找到解压后的`index.html`文件
3. 将其重命名为`booking.html`（或任何您喜欢的名称，如`shower-booking.html`）

### 步骤2：上传到GitHub

#### 方法A：使用GitHub网站上传

1. 登录您的GitHub账号
2. 进入您的仓库页面
3. 点击"Add file"按钮，然后选择"Upload files"
4. 拖拽或选择重命名后的`booking.html`文件以及其他必要的文件（如CSS、JS文件等）
5. 滚动到页面底部，添加提交信息（如"添加洗浴预约功能"）
6. 点击"Commit changes"按钮完成上传

#### 方法B：使用Git命令行上传

1. 打开命令行工具（如Git Bash、Terminal等）
2. 导航到您的本地仓库目录
3. 复制重命名后的文件到仓库目录：
   ```bash
   cp /path/to/your/shower_booking_app_v2/booking.html /path/to/your/github/repo/
   ```
4. 添加文件到暂存区：
   ```bash
   git add booking.html
   ```
5. 提交更改：
   ```bash
   git commit -m "添加洗浴预约功能"
   ```
6. 推送到GitHub：
   ```bash
   git push origin main
   ```

## 方法二：创建新的分支上传

如果您想在不影响主分支的情况下上传文件，可以创建一个新的分支。

### 步骤1：创建新分支

#### 方法A：使用GitHub网站创建分支

1. 登录您的GitHub账号
2. 进入您的仓库页面
3. 点击分支下拉菜单（通常显示为"main"或"master"）
4. 在文本框中输入新分支名称（如"booking-feature"）
5. 点击"Create branch: booking-feature"按钮

#### 方法B：使用Git命令行创建分支

1. 打开命令行工具
2. 导航到您的本地仓库目录
3. 创建并切换到新分支：
   ```bash
   git checkout -b booking-feature
   ```

### 步骤2：上传文件到新分支

按照方法一中的步骤上传文件，但确保您是在新创建的分支上操作。

### 步骤3：创建Pull Request（可选）

如果您想将新分支的更改合并到主分支，可以创建Pull Request：

1. 在GitHub仓库页面，点击"Compare & pull request"按钮
2. 填写PR描述，说明您添加了什么功能
3. 点击"Create pull request"按钮
4. 审核通过后，可以点击"Merge pull request"按钮将更改合并到主分支

## 方法三：使用子目录上传

如果您想更好地组织文件，可以将预约应用放在一个子目录中。

### 步骤1：创建子目录

1. 在您的本地仓库中创建一个新的子目录，如"booking"或"shower-booking"
2. 将解压后的所有文件复制到这个子目录中

### 步骤2：上传子目录

按照方法一中的步骤上传整个子目录。

### 步骤3：更新链接

如果您的应用中有任何相对路径的链接，可能需要更新这些链接以适应新的目录结构。

## 注意事项

1. **文件路径**：确保所有相对路径的引用都正确，特别是CSS、JavaScript和图片文件的引用
2. **GitHub Pages**：如果您使用GitHub Pages，需要确保配置正确，指向正确的文件或目录
3. **测试**：上传后，务必测试所有功能，确保一切正常工作
4. **备份**：在进行任何更改之前，建议备份您的仓库

## 故障排除

1. **文件上传失败**：
   - 检查文件大小是否超过GitHub的限制（通常为25MB）
   - 确保您有足够的权限上传到仓库

2. **链接错误**：
   - 检查所有相对路径的引用
   - 使用浏览器的开发者工具查看是否有404错误

3. **GitHub Pages不显示新页面**：
   - 检查GitHub Pages的配置，确保指向正确的文件或目录
   - 等待几分钟，GitHub Pages可能需要一些时间来更新

如果您在上传过程中遇到任何问题，请参考GitHub的[官方文档](https://docs.github.com/cn/github/managing-files-in-a-repository)或联系GitHub支持。