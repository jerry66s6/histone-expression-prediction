# 🧬 Histone-Based Gene Expression Prediction

This project applies deep learning to predict gene expression levels from histone modification signals using Transformer-based architectures.

## 📁 Dataset

- Input: Histone mark signals (3 × 100 window)
- Output: Normalized gene expression
- Preprocessed into train/val/test splits

## 🧠 Model Architecture

- Residual CNN for signal feature extraction
- Transformer Encoder with 10 layers
- Multi-head Attention Pooling (4 heads)
- Regressor with LayerNorm and Dropout
- Positional encoding included
- **Loss**: Combined MSE and Pearson correlation
- **Optimizer**: Adam + weight decay + LR scheduler
- **Early stopping**: Enabled

## 🌱 Ensemble Strategy

- Trained 5 models with different seeds
- Averaged predictions for robust generalization

## 📊 Evaluation Metrics

| Metric        | Validation | Test   |
|---------------|------------|--------|
| Pearson R     | ~0.80      | **0.8050** |
| Spearman R    | ~0.80      | **0.8051** |
| R² Score      | —          | **0.6469** |

## 📈 Visualizations

- ✅ Ensemble prediction vs. ground truth scatter plot
- ⏳ Training & validation loss tracking (optional)
- 📉 Performance comparisons

## 📎 Files

- `model_seed*.pt`: model checkpoints (not uploaded)
- `ensemble_predictions.csv`: test inputs, labels, predictions
- `scatter_plot.png`: ensemble visualization
- `README.md`: project overview

## 💡 Future Work

- Add training/validation loss curves
- Experiment with alternative input representations
- Try larger models or unfreezing pretrained encoders

---

If you use this project or find it helpful, feel free to ⭐️ the repo or cite it in your own work.
