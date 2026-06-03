# Fast-SCNN Robustness Analysis on VDD

This project evaluates the **Fast-SCNN** semantic segmentation model on the **Varied Drone Dataset (VDD)**, focusing on robustness against real-world UAV environmental corruptions.

## 🚀 Project Highlights
- **Model:** Fast-SCNN (0.09M parameters)
- **Performance:** ~245.2 FPS on CUDA
- **Corruptions Evaluated:** Fog, Rain, Snow, Brightness, Contrast, Shadow, Noise, Blur, JPEG.
- **Key Finding:** Snow is the most damaging corruption (mIoU drop of 0.1936), while JPEG compression is the least damaging.
- **Improvement:** Data augmentation increased robustness by an average of **0.0729 mIoU** across all corruptions.

## 📊 Results Summary
| Corruption | Clean mIoU | Corrupted mIoU | After Aug | Improvement |
| :--- | :--- | :--- | :--- | :--- |
| fog | 0.3533 | 0.1738 | 0.2565 | +0.0827 |
| rain | 0.3533 | 0.2358 | 0.3137 | +0.0779 |
| snow | 0.3533 | 0.1597 | 0.2927 | +0.133 |
| brightness_drop | 0.3533 | 0.1837 | 0.2666 | +0.0829 |
| contrast_loss | 0.3533 | 0.1899 | 0.2717 | +0.0818 |
| shadow | 0.3533 | 0.2586 | 0.3213 | +0.0627 |
| gaussian_noise | 0.3533 | 0.1914 | 0.2712 | +0.0798 |
| motion_blur | 0.3533 | 0.2447 | 0.2791 | +0.0344 |
| jpeg_compress | 0.3533 | 0.3254 | 0.3463 | +0.0209 |

## 📁 Directory Structure
```text
.
├── configs/            # Model and training configurations
├── datasets/           # VDD Source images and Ground Truth
├── models/             # Architecture definitions
├── outputs/
│   ├── checkpoints/    # Saved .pth weights (Baseline & Augmented)
│   └── predictions/    # Sample segmentation outputs
├── results/            # Performance charts and Project_Report.pdf
└── scripts/            # Helper utilities
```

## 🛠️ Setup
1. Install requirements: `pip install torch albumentations fpdf2`
2. Configure `PROJECT_ROOT` in the notebook to point to your data.
3. Run evaluation cells to reproduce metrics.

---
*Developed as part of the VDD Robustness Study.*