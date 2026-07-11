# LettucePlayer Releases

生菜播放器 / LettucePlayer 是一款面向 Windows 的轻量绿色视频预览播放器，用于快速回看影视设备拍摄的视频素材。它重点改善 Log、HLG、PQ / HDR 等素材在普通播放器中灰暗、曝光观感不直观的问题，适合拍摄现场、素材筛选和后期制作前的快速预览，提供LUT快速套用和基础监看功能，并提供视频渲染信息细节，适配当前主流播放器操作习惯。

本仓库是 LettucePlayer 的官方二进制发布渠道。

## 核心特性

- **绿色免安装**：解压即可运行，不写入注册表，不自动关联视频格式。
- **面向拍摄素材**：支持打开单个视频、拖入多个文件或整个文件夹，并通过当前目录素材列表快速切换。
- **Log / HLG / HDR 预览**：基于 mpv `gpu-next`、D3D11 和 libplacebo 渲染，提供自动处理和可手动选择的 SDR Preview / Tone Mapping 预设。
- **\.cube LUT**：扫描程序目录下的 `luts/` 文件夹，支持按子目录浏览、搜索、启用和快速切换；手动选择后立即应用。
- **基础画面调整**：提供对比度、Gamma、饱和度、重置和文件夹预设；这些操作只改变预览效果。
- **监看辅助**：提供最终输出画面的 RGB 波形图、直方图和伪色辅助，以及渲染管线、色彩、解码和 mpv 诊断信息。
- **常用播放操作**：播放/暂停、定位、逐帧、音量、静音、音轨、字幕显隐、上一/下一素材、全屏、截图和预览旋转。
- **多语言界面**：支持简体中文、日本語和 English。
- **保护原始素材**：播放器不会覆盖、移动、删除视频，不向素材目录写入元数据，也不会自动转码或重封装。

> LettucePlayer 的定位是“快速、直观地预览素材”，不是剪辑、调色、转码或素材管理软件。画面处理结果不应替代专业母版、广播合规或色彩精确验收；首版也不支持 RAW 视频或 HDR 显示器输出工作流。

## 快速开始

1. 从 [Releases 页面](https://github.com/zhouzhou514/LettucePlayer-Releases/releases)下载明确列在 **Assets** 下的 Windows x64 绿色包。
2. 将 ZIP **完整解压**到一个可写目录，不要直接在压缩包内运行。
3. 运行 `LettucePlayer.exe`。
4. 通过文件选择器打开视频，或把视频文件/文件夹直接拖入播放器。
5. 使用右侧素材浏览器切换当前目录中的视频；使用底部控制栏完成播放、定位、音量、音轨、字幕和全屏操作。
6. 如需 LUT，把 `.cube` 文件放入播放器目录下的 `luts/`；可以用子文件夹分类。若播放器已启动，请重启后再从 LUT 面板选择。
7. 使用左侧检查器查看元数据、渲染管线、LUT、Tone Mapping、画面调整、监看辅助和 mpv 诊断。
8. 截图默认写入播放器目录下的 `screenshots/`，配置和日志分别位于 `config/` 与 `logs/`。

首次运行建议先用一段熟悉的 SDR、HLG 或 Log 素材检查播放和预览效果。硬件解码默认由 mpv 自动选择；若初始化或播放失败，请查看错误提示和 `logs/`，并在提交 Issue 时移除私人路径、文件名和其他敏感信息。

## 常用操作

- 双击视频区域：播放/暂停。
- 在视频区域横向拖动：相对定位。
- `Alt + 滚轮`：缩放画面。
- `Alt + 左键拖动`：平移画面。
- `Alt + 中键`：重置视图。
- `L`：切换 LUT。
- `O`：切换 Tone Mapping。
- `P`：切换手动画面调整。
- `C`：切换字幕。
- `M`：静音。
- `Alt + M`：显示/隐藏监视器窗口。

播放器内的快捷键帮助列出了完整的播放、浏览、逐帧、画面处理和监看操作。

## 系统与运行边界

- 目标平台：Windows 11 x64。
- 采用绿色包发布，包内包含所需的 .NET 桌面运行时，通常无需另行安装 .NET Desktop Runtime。
- 仍依赖系统 D3D11 能力和可用的显卡驱动。
- 第一版不支持 N-RAW、ProRes RAW、BRAW、R3D 等 RAW 视频。
- 第一版不提供剪辑、导出、转码、专业节点调色、完整 OCIO / ACES / ICC 色彩管理或 HDR 输出。

## Repository scope

This repository is used only for:

- official portable Windows release packages;
- release notes and checksums;
- application license and support information;
- third-party license notices;
- corresponding source and build materials for bundled open-source components.

The source code of the LettucePlayer application body is not hosted in this repository. This repository is not the development or source-code repository of LettucePlayer.

## Application license

The LettucePlayer application body is proprietary software.

Personal non-commercial use is free. Commercial organizations and commercial or profit-related use require explicit authorization from the copyright holder.

The complete application license will be included as `APP-LICENSE.txt` in each release package.

## Third-party components

LettucePlayer bundles or dynamically links third-party components including mpv, FFmpeg, libplacebo, MediaInfoLib and Microsoft .NET runtime components.

Those components are licensed independently under their respective licenses. The LettucePlayer application license does not restrict rights granted by those third-party licenses.

Corresponding source archives, original license texts, build information and notices for the exact bundled versions will be provided with each applicable public release.

## Downloads

No binary package has been published yet.

When releases become available, use the files explicitly listed under **Assets** on the [Releases page](https://github.com/zhouzhou514/LettucePlayer-Releases/releases).

GitHub automatically displays “Source code (zip)” and “Source code (tar.gz)” for repository metadata. Those automatically generated archives are not the LettucePlayer application package and do not contain its proprietary source code.

## Issues

The [Issues page](https://github.com/zhouzhou514/LettucePlayer-Releases/issues) is available for public bug reports and release-related feedback. Do not submit private media, logs containing personal paths, account data, customer materials, commercial secrets or other sensitive information.

## Security

Future releases will publish SHA-256 checksums. Verify the checksum before running a downloaded package.
