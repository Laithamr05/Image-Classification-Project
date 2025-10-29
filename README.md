# 🌼 Image Classifier Project (Oxford Flowers 102)

This project is a deep learning image classifier built with **TensorFlow**, **TensorFlow Hub**, and **Keras**.  
It uses transfer learning to classify **102 flower categories** from the Oxford Flowers dataset.

---

## 📂 Project Structure

```
├── assets/                     # Supporting files (e.g., model architecture or visualizations)
├── test_images/                # Sample test flower images for predictions
├── Project_Image_Classifier_Project.ipynb  # Jupyter notebook for training and experimentation
├── predict.py                  # Command-line script to make predictions
├── label_map.json              # Maps class indices to flower names
├── saved_keras_model.h5        # Saved trained model
```

---

## 🧠 Project Overview

The model uses **transfer learning** with a pretrained CNN feature extractor (such as `mobilenet_v2` or `inception_v3`) from TensorFlow Hub.  
After training, the model can accurately classify a flower image into one of 102 species.

### Main Steps:
1. Load and preprocess the **Oxford Flowers 102** dataset  
2. Use a pretrained CNN model as a base  
3. Add custom classifier layers  
4. Train the network on flower images  
5. Save the trained model (`saved_keras_model.h5`)  
6. Implement prediction using the command-line script

---

## ⚙️ Requirements

Make sure you have these dependencies installed:
```bash
pip install tensorflow tensorflow-hub tensorflow-datasets matplotlib numpy pillow
```

---

## 🚀 How to Run

### 1. Train the Model
Run the Jupyter Notebook:
```bash
jupyter notebook Project_Image_Classifier_Project.ipynb
```

### 2. Make Predictions
Use the command-line script `predict.py`:
```bash
python predict.py --image_path test_images/image_07874.jpg --model saved_keras_model.h5 --top_k 5 --category_names label_map.json
```

**Arguments:**
- `--image_path`: Path to the image you want to classify  
- `--model`: Path to the trained model  
- `--top_k`: (optional) Return top K predictions  
- `--category_names`: (optional) JSON file mapping labels to flower names  

---

## 🌸 Example Output

```
Top K Predictions:
1. Pink Primrose — 85.2%
2. Hibiscus — 7.6%
3. Water Lily — 4.1%
```

---

## 📊 Results

The final model achieved high accuracy (>85%) on the validation dataset.  
The combination of transfer learning and data augmentation improved performance significantly compared to training from scratch.
