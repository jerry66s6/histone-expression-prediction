# Histone Expression Prediction using Transformer-Based Deep Learning

This project presents a deep learning pipeline to predict **gene expression levels** from **histone modification signals** using an advanced Transformer architecture. The approach combines CNN preprocessing, multi-head attention pooling, and transformer encoders to model complex genomic patterns.

---

## 🧬 Motivation

Histone modifications regulate gene expression by altering chromatin structure and accessibility. Modeling this relationship is essential for understanding epigenetic regulation. This project uses deep learning to predict expression levels from 3-channel histone signal tracks over genomic regions.

---

## 📁 Dataset

- Input: Histone mark signals over 100 bp bins (3 channels)
- Target: Normalized gene expression values (zero mean, unit variance)
- Split: 81% training, 9% validation, 10% test

---

## 🧠 Model Architecture

- **Residual CNN** for spatial feature extraction
- **Transformer Encoder** with 10 layers and 8 attention heads
- **Multi-Head Attention Pooling** for global representation
- **Regression Head** to predict continuous expression level
- **Loss Function**: Weighted combination of MSE and Pearson correlation

---

## 🔁 Training Strategy

- Optimizer: Adam with weight decay `1e-4`
- Scheduler: ReduceLROnPlateau
- Early Stopping: Patience = 5
- Ensemble of 5 models trained with different seeds
- Final evaluation done on averaged ensemble prediction

---

## 📊 Evaluation Metrics

- **Pearson Correlation** (Test): `0.8050`
- **Spearman Correlation** (Test): `0.8051`
- **R² Score**: `0.6469`

---

## 📈 Results

<p align="center">
  <img src="scatter_plot.png" alt="Ensemble Prediction Scatter" width="500"/>
</p>

The ensemble prediction closely matches the true expression values, demonstrating the model's ability to generalize and capture biological signals.

---

## 🚀 Future Directions

- Incorporate additional epigenetic tracks (e.g. DNase, methylation)
- Use genome-wide data across more cell types
- Apply this pipeline to disease-specific expression studies

---

## 📦 Files Included

- `main_model.py`: Model architecture and training loop
- `ensemble_eval.py`: Ensemble inference and correlation metrics
- `scatter_plot.png`: Final ensemble prediction scatter plot
- `README.md`: Project documentation

---

## 🧪 Author Notes

This project is developed as part of a Ph.D. research initiative to explore deep learning applications in computational epigenomics. Feedback and collaboration are welcome!

