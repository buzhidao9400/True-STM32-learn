# True-STM32-learn

电控培训代码仓库。用于存放培训期间的 STM32 实验代码，供队里收集链接审查进度。

## 仓库结构

每个实验单独放一个文件夹，里面是一份完整的可独立编译工程：

```
True-STM32-learn/
├── .gitignore
├── README.md
└── first/              # 实验工程（STM32F103C8T6 蓝 Pill，CMake + OpenOCD）
    ├── Core/           # 用户代码：在 main.c 的 USER CODE 区写功能
    ├── Drivers/        # STM32 HAL / CMSIS 库
    ├── cmake/          # ARM 工具链配置
    ├── CMakeLists.txt
    ├── CMakePresets.json
    ├── first.ioc       # STM32CubeMX 配置
    ├── openocd.cfg     # 烧录/调试配置（ST-Link + STM32F1）
    └── .vscode/        # F7 编译 / F8 烧录 / F5 调试
```

## 如何提交一个新实验

1. 复制现有实验文件夹（如 `first/`）为新文件夹，例如 `lab01_led/`
2. 在里面的 `Core/Src/main.c` 的 `/* USER CODE BEGIN ... */` 与 `/* USER CODE END ... */` 之间写功能代码
3. 在 VS Code 源代码管理面板提交并推送（或命令行 `git add` → `git commit` → `git push`）
4. 把本仓库链接填进队里的 GitHub 仓库链接收集表

## 编译 / 烧录 / 调试（在实验文件夹内）

- **F7**：编译（CMake: build）
- **F8**：烧录（OpenOCD: flash）
- **F5**：调试（Cortex-Debug）

> 注意：`build/` 等编译产物已在 `.gitignore` 中排除，无需上传；VS Code 打开本仓库根目录即可管理所有实验。
