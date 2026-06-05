
# Clasificación de Lesiones Cutáneas con CNNs | Transfer Learning + HAM10000 | Deep Learning

Proyecto final del módulo de Redes Neuronales Convolucionales —  
Fundamentos de Deep Learning | Universidad de Antioquia  
**Estudiante:** Diego Alejandro Rendón Suaza  
**Profesores:** Raúl Ramos | Julián Arias  

---

## 🎥 Video de presentación

[![Video presentación](https://img.youtube.com/vi/bIFsZNIb_10/0.jpg)](https://youtu.be/bIFsZNIb_10)

👉 [https://youtu.be/bIFsZNIb_10](https://youtu.be/bIFsZNIb_10)

---

## 📋 Descripción

Sistema de clasificación automática de lesiones cutáneas pigmentadas  
usando el dataset **HAM10000** (10,015 imágenes dermatoscópicas, 7 clases diagnósticas).

El proyecto compara sistemáticamente distintas arquitecturas CNN y evalúa  
el efecto de las estrategias de mitigación del desbalance de clases.

---

## 🔬 Iteraciones del proyecto

| # | Notebook | Descripción |
|---|---|---|
| 1 | `01_exploracion_y_preprocesado.ipynb` | EDA, verificación RGB, split por `lesion_id`, pesos de clase |
| 2 | `02_arquitectura_linea_base_binaria.ipynb` | CNN desde cero — comparativa sin/con pesos de clase |
| 3 | `03_transfer_learning_binario.ipynb` | VGG16 vs ResNet50 vs EfficientNet-B0 |
| 4 | `04_clasificacion_multiclase.ipynb` | ResNet50 + fine-tuning progresivo — 7 clases |

---

## 📊 Resultados principales

### Iteración 1 — CNN Baseline (efecto de pesos de clase)
| Métrica | Sin pesos | Con pesos |
|---|---|---|
| Balanced Accuracy | 0.500 | **0.644** |
| Recall Maligno | 0.00 | **0.49** |
| AUC-ROC | 0.822 | 0.772 |

### Iteración 2 — Transfer Learning Binario
| Modelo | Balanced Acc | F1 Macro | AUC-ROC |
|---|---|---|---|
| VGG16 | 0.734 | 0.677 | 0.807 |
| **ResNet50** | 0.745 | **0.725** | **0.850** |
| EfficientNet-B0 | **0.769** | 0.695 | 0.842 |

### Iteración 3 — ResNet50 Multiclase (7 clases)
| Métrica | Valor |
|---|---|
| Accuracy | 0.7427 |
| Balanced Accuracy | 0.6937 |
| F1-Score Macro | 0.6024 |
| **AUC-ROC Macro (OvR)** | **0.9494** |

---

## 🛠️ Stack tecnológico

- Python 3.12
- PyTorch + torchvision
- scikit-learn
- pandas + matplotlib + seaborn
- Google Colab (CPU/GPU)

---

## 🚀 Cómo reproducir

1. Abre cualquier notebook en **Google Colab**
2. Configura tus credenciales de Kaggle en **Secrets**:
   - `KAGGLE_USERNAME` → tu usuario
   - `KAGGLE_KEY` → tu API key
   - *(Si no tienes cuenta de Kaggle, el notebook usa Google Drive automáticamente)*
3. Activa GPU: `Entorno de ejecución → T4 GPU`
4. Ejecuta **Run all**

El dataset se descarga automáticamente.  
Semilla fija `SEED=42` — resultados reproducibles.

---

## 📁 Estructura del repositorio

```
├── 01_exploracion_y_preprocesado.ipynb
├── 02_arquitectura_linea_base_binaria.ipynb
├── 03_transfer_learning_binario.ipynb
├── 04_clasificacion_multiclase.ipynb
├── INFORME_PROYECTO.PDF
├── ENTREGA1.PDF
└── README.md
```

---

## 📚 Referencias

1. Tschandl et al. (2018). The HAM10000 dataset. *Scientific Data*. doi:10.1038/sdata.2018.161  
2. Esteva et al. (2017). Dermatologist-level classification of skin cancer. *Nature*, 542, 115–118.  
3. He et al. (2016). Deep Residual Learning for Image Recognition. *CVPR 2016*.  
4. Simonyan & Zisserman (2014). Very Deep Convolutional Networks. arXiv:1409.1556.  
5. Tan & Le (2019). EfficientNet. *ICML 2019*. arXiv:1905.11946.
```
