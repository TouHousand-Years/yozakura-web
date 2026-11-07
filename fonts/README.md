# 游戏像素字体

网页版兼容抓图另用构建生成的 `src/assets/font/capture.woff2` 字体子集，只保留当前源码和 JSON 内容会用到的字符，随构建自动更新。构建逐字验证轮廓、字宽和字体行度量，原网页字体不变。子集沿用 SIL OFL 1.1，保留原版权和许可信息；它是字体的裁剪版本。此文件经 Vite 以带哈希文件名发布，不会与旧版本缓存混用。

使用 [Fusion Pixel Font](https://github.com/TakWolf/fusion-pixel-font/releases/tag/2026.10.16) 2026.10.16 的 `fusion-pixel-12px-monospaced-zh_hans.otf.woff2`，未经修改。

字体随应用离线打包；采用 SIL Open Font License 1.1，见 `OFL.txt`，上游字形许可见 `LICENSES/`。

游戏与原型画布均按 12px 字号、16px 行距显示。全宽字符占 12 个逻辑像素，半宽字符占 6 个；禁止合成粗体与字偶距调整。游戏首次渲染前等待字体加载，以便按钮按实际字体测量宽度。

这里的像素指 853×480 画布上的逻辑像素。480P、960P、1440P 分别为 1、2、3 倍；全屏的非整数缩放仍可能导致物理屏幕上的笔画插值。
