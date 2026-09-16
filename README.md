<p align="center">
  <img src="./assets/readme/hero.svg" width="100%" alt="霜璃 Codex v2 动态宠物：9 组动画、16 个观察方向和透明 WebP 图集">
</p>

# 霜璃 · Codex 动态宠物

霜璃是一只白发紫瞳、带双角、小翼与蓬松鳞尾的 Q 版龙族少女宠物。仓库交付一个 Codex 宠物包：运行时只需要根目录的 `pet.json` 和 `spritesheet.webp`。

## 先看结果

![霜璃动作总览](assets/contact-sheet.png)

当前包使用 Codex 宠物图集格式 v2（`spriteVersionNumber: 2`），包含 9 组标准动画、16 个观察方向和透明 RGBA WebP 图集。验证记录显示图集为 8 × 11 网格、总尺寸 `1536 × 2288`，没有透明残留错误。

## 最简单的安装方法（Windows）

1. 点击 GitHub 页面右上方 **Code → Download ZIP**。
2. 解压下载文件。
3. 打开 `%USERPROFILE%\.codex\pets\`。
4. 新建文件夹 `shuangli`。
5. 把仓库根目录中的 `pet.json` 和 `spritesheet.webp` 复制到 `shuangli` 文件夹。
6. 重新打开 Codex。

安装完成后的关键目录应为：

```text
%USERPROFILE%\.codex\pets\shuangli\
├── pet.json
└── spritesheet.webp
```

如果已经安装 Git，也可以直接运行：

```powershell
git clone https://github.com/liangjie78/shuangli-codex-pet.git "$env:USERPROFILE\.codex\pets\shuangli"
```

> 该安装方式适用于支持本地 v2 宠物包的 Codex 桌面环境。仓库中的预览图片、GIF 和验证文件不是运行必需文件。

## 动画与方向预览

| 待机 | 左右移动 | 挥手 | 跳跃 |
| --- | --- | --- | --- |
| ![待机](previews/idle.gif) | ![向右移动](previews/running-right.gif) | ![挥手](previews/waving.gif) | ![跳跃](previews/jumping.gif) |

| 失败 | 等待 | 工作中 | 复核 |
| --- | --- | --- | --- |
| ![失败](previews/failed.gif) | ![等待](previews/waiting.gif) | ![工作中](previews/running.gif) | ![复核](previews/review.gif) |

完整的 16 向观察效果见 [方向预览图](assets/look-directions.png)。图集单格为 `192 × 208`，完整图集为 `1536 × 2288`。

## 文件说明

```text
.
├── pet.json                 # Codex 宠物配置，id 为 shuangli
├── spritesheet.webp         # 实际运行图集
├── validation.json          # v2 图集验证结果
├── SHA256SUMS.txt           # 图集完整性校验值
├── assets/                  # 静态总览与方向预览
└── previews/                # 9 组动画 GIF
```

验证图集完整性：

```powershell
(Get-FileHash .\spritesheet.webp -Algorithm SHA256).Hash
```

结果应与 `SHA256SUMS.txt` 中的值一致。

## 常见问题

**Codex 中没有出现宠物？**

检查 `pet.json` 和 `spritesheet.webp` 是否直接位于 `shuangli` 文件夹中，而不是多嵌套了一层仓库目录；然后重新打开 Codex。

**可以只下载两个文件吗？**

可以。运行时只需要仓库根目录的 `pet.json` 和 `spritesheet.webp`。

**怎样验证图集没有损坏？**

使用上面的 PowerShell 哈希命令，并与仓库中的 `SHA256SUMS.txt` 比较。

## 素材与权利说明

本仓库包含根据用户提供的角色参考图生成的派生宠物素材。仓库公开访问不代表授予商业使用、再授权或角色权利；使用时请尊重原始图片作者与相关权利人的权益。

仓库未附带开源许可证，因此除 GitHub 正常浏览、下载和个人安装外，不默认授予其他许可。

## 相关链接

- [OpenAI Codex 官方介绍与安装](https://learn.chatgpt.com/zh-Hans/docs/codex/cli)
