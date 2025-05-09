# chest-X-rays-for-pneumonia
# AI-Powered Diagnostic Tool for Medical Imaging: Reducing Diagnostic Errors in Radiology

## 1. Scope
- Focus on chest X-rays
- Detect pneumonia

## 2. Dataset
- **NIH Chest X-ray Dataset** (download to `data/raw/`):
  https://nihcc.app.box.com/v/ChestXray-NIHCC

## 3. Preprocessing
- Resize to 224×224, normalize pixel values
- Data augmentation (rotation, flip, contrast)
- (Optional) ROI segmentation

## 4. Model
- CNN built with Keras
- Input shape: 224×224×1, output: 2 classes

## 5. Training & Evaluation
- Split into training/validation/testing
- Metrics: accuracy, sensitivity, specificity, F1-score
- Threshold tuning to reduce false positives/negatives

## 6. Improvements
- Transfer learning (e.g. pretrained ResNet)
- Ensemble models

## 7. Deployment
- Flask app in `src/app.py` for uploading and predicting

## 8. Documentation
- Introduction, methodology, results, discussion, future work
- Use GitHub for version control and issues

### Tools
- Python, Jupyter Notebook
- Keras (TensorFlow)
- Flask

### Quick Start
```bash
pip install -r requirements.txt
python src/data_loader.py --input_dir data/raw --output_dir data/processed
python src/train.py --data_dir data/processed --epochs 20 --batch_size 32
python src/evaluate.py --model_path models/best_model.h5 --data_dir data/processed
python src/app.py  # starts Flask server
