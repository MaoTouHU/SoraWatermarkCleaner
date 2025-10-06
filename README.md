
# SoraWatermarkCleaner

English | 中文  

This project provides an elegant AI-powered way to remove the watermark in Sora2-generated videos.  
本项目提供了一种基于AI的优雅方案，用于去除Sora2生成视频中的水印。  

It uses deep learning models to automatically detect and seamlessly restore video content.  
通过深度学习模型自动检测并无痕修复视频内容。  

SoraWatermarkCleaner is open-source, lightweight, and easy to use with both CLI and Web UI.  
SoraWatermarkCleaner 是一个开源、轻量且易用的工具，支持命令行和Web界面操作。  

Achieve professional-grade watermark removal and restore original video quality effortlessly.  
实现专业级水印去除效果，轻松恢复视频原始质量。  

---

- Watermark Removed / 去除水印示例  
https://github.com/user-attachments/assets/8cdc075e-7d15-4d04-8fa2-53dd287e5f4c  

- Original / 原始视频  
https://github.com/user-attachments/assets/3c850ff1-b8e3-41af-a46f-2c734406e77d  

---

## 1. Method / 方法说明

The SoraWatermarkCleaner (we call it `SoraWm`) consists of two main components:  
SoraWatermarkCleaner（以下简称 `SoraWm`）主要由以下两部分组成：  

- **SoraWaterMarkDetector**: A YOLOv11s-based model trained to detect the Sora watermark. (Thanks to YOLO!)  
  **SoraWaterMarkDetector**：基于 YOLOv11s 训练的水印检测模型。（感谢 YOLO 项目！）  

- **WaterMarkCleaner**: Uses the LAMA model (from [IOPaint](https://github.com/Sanster/IOPaint)) for watermark removal and inpainting.  
  **WaterMarkCleaner**：基于 [IOPaint](https://github.com/Sanster/IOPaint) 的 LAMA 模型实现水印去除与画面修复。  

The system is fully deep-learning-driven and achieves excellent results on various generated videos.  
整个系统完全由深度学习驱动，在多种生成视频上均取得了出色效果。  

---

## 2. Installation / 安装说明

We recommend using `uv` to manage dependencies.  
建议使用 `uv` 管理项目依赖。  

### 1️⃣ Install environment / 安装环境
```bash
uv sync
source .venv/bin/activate
````

### 2️⃣ Download pretrained models / 下载预训练模型

The YOLO weights (`best.pt`) and LAMA model are downloaded automatically.
YOLO 权重（`best.pt`）与 LAMA 模型将自动下载。

If download fails, please check your internet connection.
若下载失败，请检查网络连接。

---

## 3. Demo / 示例演示

You can run a demo using `example.py`:
可运行 `example.py` 进行基本演示：

```python
from pathlib import Path
from sorawm.core import SoraWM

if __name__ == "__main__":
    input_video_path = Path("resources/dog_vs_sam.mp4")
    output_video_path = Path("outputs/sora_watermark_removed.mp4")
    sora_wm = SoraWM()
    sora_wm.run(input_video_path, output_video_path)
```

You can also try the Streamlit-based web interface:
也可通过 Streamlit 启动交互式网页界面：

```bash
streamlit run app.py
```

<img src="resources/app.png" style="zoom:25%;" />

---

## 4. License / 许可协议

Apache License 2.0

---

## 5. Citation / 引用方式

```bibtex
@misc{sorawatermarkcleaner2025,
  author = {linkedlist771},
  title = {SoraWatermarkCleaner},
  year = {2025},
  url = {https://github.com/linkedlist771/SoraWatermarkCleaner}
}
```

---

## 6. Acknowledgments / 致谢

* [IOPaint](https://github.com/Sanster/IOPaint) for the LAMA implementation
  感谢 IOPaint 团队提供的 LAMA 实现。
* [Ultralytics YOLO](https://github.com/ultralytics/ultralytics) for object detection
  感谢 Ultralytics YOLO 团队提供的目标检测框架。

---

### ✨ Keywords / 关键词

Sora2 watermark removal, AI watermark cleaner, deep learning video restoration,
视频去水印, AI视频修复, 深度学习水印清除, 视频无痕修复, Sora2视频编辑, 开源AI工具

 
