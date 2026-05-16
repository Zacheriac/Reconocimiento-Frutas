# Reconocimiento-Frutas
#  Clasificador de Frutas y Verduras con CNN + Transfer Learning

## Descripción
Sistema de clasificación automática de frutas y verduras mediante 
imágenes, utilizando Redes Neuronales Convolucionales (CNN) con 
Transfer Learning (MobileNetV2). El modelo identifica la fruta/verdura 
específica (T2) y su categoría de sabor (T1).

## Objetivos
- **T1 — Etiqueta padre:** clasificar por sabor (dulce / ácida / neutra)
- **T2 — Etiqueta hijo:** identificar la fruta o verdura específica 
  entre 36 clases

##  Dataset
- **Fuente:** [Fruit and Vegetable Image Recognition](https://www.kaggle.com/datasets/kritikseth/fruit-and-vegetable-image-recognition)
- **Total imágenes:** ~3,115 (2,510 entrenamiento + 605 validación)
- **Clases (T2):** 36 tipos de frutas y verduras
- **Etiquetas padre (T1):** dulce · ácida · neutra · otra

### Distribución de clases T1
| Etiqueta | Frutas/Verduras incluidas |
|----------|--------------------------|
|  Dulce | Apple, Banana, Grapes, Mango, Pear, Strawberry, Watermelon |
|  Ácida | Orange, Kiwi, Lemon, Pineapple, Pomegranate, Tomato |
|  Neutra | Avocado, Coconut, Corn, Cucumber, Carrot, Potato, Spinach... |

##  Modelo
- **Arquitectura:** MobileNetV2 (preentrenado en ImageNet)
- **Técnica:** Transfer Learning — base congelada + cabeza personalizada
- **Capas añadidas:**
  - GlobalAveragePooling2D
  - Dense (256 neuronas, ReLU)
  - Dropout (40%)
  - Dense (36 salidas, Softmax)
- **Optimizador:** Adam
- **Loss:** Sparse Categorical Crossentropy
- **Épocas:** hasta 10 (con EarlyStopping)

## Técnicas aplicadas
| Técnica | Descripción |
|---------|-------------|
| Transfer Learning | Reutiliza conocimiento de MobileNetV2 entrenado con millones de imágenes |
| Data Augmentation | Rotación, zoom, volteo y variación de brillo para generalizar mejor |
| EarlyStopping | Detiene el entrenamiento automáticamente si deja de mejorar |
| Normalización | Escala píxeles de [0-255] a [0-1] para estabilizar el entrenamiento |

##  Resultados
| Métrica | Valor |
|---------|-------|
| Precisión (T2 — fruta) | X% |
| Margen de error | X% |
| Imágenes evaluadas | X |
| Reconoció correctamente | X |

> Reemplaza las X con tus valores reales al terminar el entrenamiento

##  Cómo ejecutar
1. Abrir en **Google Colab**
2. Ejecutar las celdas en orden de arriba hacia abajo
3. Esperar el entrenamiento (~10 minutos)
4. En la última celda: clic en **"Subir imagen"** → seleccionar foto → 
   clic en **"Reconocer"**

##  Requisitos
