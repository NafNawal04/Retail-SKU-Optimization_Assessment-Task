# Retail SKU Recall Optimization

Trained a YOLOv11 model(medium) to detect high-density retail stock with a focus on maximizing **Recall** for inventory accuracy.

## Results Overview
*   **Original Recall**: 67.6%
*   **Final Optimized Recall**: **79.2%** (A +11.6% improvement)
*   **mAP50**: 79.7%

## Optimization Strategy
To improve detectability of tiny and crowded SKUs, the following techniques were applied:
1.  **Resolution Scaling**: Trained at `imgsz=1024` to preserve pixel detail.
2.  **Model Choice**: Upgraded to **YOLOv11m** (Medium) for better feature extraction.
3.  **SAHI Integration**: Used Slicing Aided Hyper Inference to detect small objects in high-resolution tiles.
4.  **SAHI NMM**: Implemented Non-Maximum Merging to reduce duplicates and stabilize precision.

## Share of Shelf Analysis
Treating the test set as a single retail environment, the top SKUs found were:
1. SKU q293: 10.22%
2. SKU q214: 9.84%
3. SKU q64: 9.09%

## How to Run
1. Upload the `task.ipynb` to Kaggle.
2. Use GPU T4x2.
3. Ensure your `ROBOFLOW_API_KEY` is set as a Secret.
4. Run all cells to replicate the inference and analytics.
