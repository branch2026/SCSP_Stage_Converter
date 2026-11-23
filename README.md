# SCSP_Stage_Converter

将 SCSP 的 Unity 工程舞台批量转换为 MikuMikuDance（MMD）可用的 PMX 文件。

## 运行环境

本工具仍在开发中，目前使用 **Blender 4.4.3** 和 **MMD Tools** 插件进行测试。其他 Blender 版本尚未测试。

- 在 Windows 上使用带 Tk 的 Python 3 运行工具。
- 视频屏幕转换需要 FFmpeg。确保 `ffmpeg` 可以从 `PATH` 找到，也可以通过 `SCSP_FFMPEG` 指定 `ffmpeg.exe` 的完整路径。
- 在 MMD 中播放视频屏幕，需要安装 MikuMikuEffect（MME）。

解压发布包后，双击 `RUN_GUI.bat`。首次启动时，点击「Blender 4.4.3」旁边的「浏览」，选择本机的 `blender.exe`。

## 视频屏幕舞台

目前已测试的视频屏幕舞台均可自动识别并批量转换。批量转换时勾选以下选项。

- 包含 inactive GameObject（默认）
- 自动还原舞台效果
- 自动去除地板黑影
- 另存 MME 效果试验包

1. 转换完成后，打开对应舞台输出目录下的 `AutoStage/MME_Preview`。
2. 在 MMD 中先载入该目录里的 PMX，选中舞台模型后，再载入同目录的「屏幕播放时长」VMD。
3. 保留目录里的 EMD、FX 和贴图文件及其相对位置。部分舞台会按原演出时间延迟亮屏。

建议使用 `D:\SCSP\PMX` 这类 ASCII 输出路径。已实测带日文的输出目录可能导致 MME 屏幕显示为灰色。

## 普通舞台

普通舞台目前只支持部分舞台效果。转换时勾选「包含 inactive GameObject（默认）」「自动还原舞台效果」和「自动去除地板黑影」。部分舞台需要取消勾选「包含 inactive GameObject（默认）」后重新转换。

在 MMD 中先载入 `AutoStage` 里的处理版 PMX。如果同目录生成了 VMD，再选中舞台模型并载入该 VMD。只有基础 PMX 时，可直接载入舞台输出目录里的 PMX。

## 获取 Unity 舞台工程

可以使用 Labubu 制作的资源下载器获取 SCSP 舞台并导出为 Unity 工程。 [SCSP Resource Downloader](https://github.com/patchouliwxy/SCSP-Resource-Downloader)

## 许可

允许按照仓库 [LICENSE](LICENSE) 的条款进行二次修改和再发布。

感觉完成度好低，不过还是先发出来了。希望有人能做出更好的的版本。
