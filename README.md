# SVD 可视化

一个无需安装依赖的交互式网页，展示二维线性变换的分解过程：

```text
x → Vᵀx → ΣVᵀx → UΣVᵀx
```

依次观察旋转 / 反射、轴向缩放和最终变换。项目使用 HTML、CSS、JavaScript 和 Canvas，全部计算在浏览器中完成，无需后端服务。

## 项目目录

```text
项目根目录/
├── docs/
│   └── index.html   # 网页结构、样式、矩阵运算和绘图
└── README.md        # 使用与发布说明
```

## 本地使用

双击 `docs/index.html`，用浏览器打开即可离线使用。

- 控制区按 V → Σ → U 排列。编辑 U、V 的任意元素，按 Enter 或离开输入框后生效；其余元素自动调整以保持正交性。
- U、V 显示小数点后三位，内部计算保留完整精度。
- 拖动 σ₁、σ₂ 滑块或直接输入 0 到 5 之间的数值。两个奇异值均为非负数，可独立调整，不强制降序排列。
- 使用 U、V 的反射选项观察镜像变换。
- V、Σ、U 各有独立重置按钮，也可以使用总体重置。
- 四幅图共用坐标范围；左上角的 ± 数值表示横、纵坐标的显示范围。
- 默认示例图背景透明。可选择自己的图片，图片仅在本地读取并保持宽高比，显示用副本的最长边限制为 800 像素。

本项目用于展示二维几何变换，不会从任意输入矩阵自动求解 SVD，也不是图片低秩压缩工具。刷新页面会恢复默认设置。

## 上传到 GitHub

1. 登录 GitHub，新建仓库，例如 `svd-visualization`。使用免费账户发布时，将仓库设为 **Public**。
2. 在新仓库页面点击 **uploading an existing file**；已有文件的仓库可点击 **Add file → Upload files**。
3. 拖入本地的 `docs` 文件夹和 `README.md`，填写提交说明，点击 **Commit changes**。
4. 确认仓库根目录下存在 `docs/index.html` 和 `README.md`。保留 `docs` 文件夹层级，不要只把 `index.html` 放到仓库根目录。

只需上传上述文件，无需上传本地环境配置。

## 发布到 GitHub Pages

1. 进入仓库 **Settings → Pages**。
2. 在 **Build and deployment → Source** 中选择 **Deploy from a branch**。
3. 选择上传文件的分支（通常为 `main`），文件夹选择 **/docs**，点击 **Save**。
4. 等待部署完成，打开 Pages 设置页显示的网站链接。也可以在仓库 **Actions** 中查看部署进度。

默认项目网址的格式为：

```text
https://你的用户名.github.io/svd-visualization/
```

仓库名不同，网址最后一段也相应改变。可以把实际网址放到 README 或仓库的 About 网站栏中，方便访问者打开。

如果这是较大仓库中的子目录，请将这里的 `docs/index.html` 放到仓库根目录的 `docs/index.html`，或合并到已有的网站目录；不要覆盖已有首页。

以后修改 `docs/index.html`，提交到发布分支后，GitHub Pages 会自动重新发布。网页访客调整参数不会修改仓库文件。

参考：[GitHub Pages 简介](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)、[发布源配置](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)。
