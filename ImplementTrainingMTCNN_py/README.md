# MTCNN_Training_Bach
MTCNN – P-Net Training and R-Net Dataset Generation
Autores: Michell A. y Silvana R.
# Descripción general

Este proyecto implementa la etapa P-Net del modelo MTCNN y el pipeline completo de generación, filtrado y análisis de propuestas, con el objetivo de construir el dataset de entrenamiento para R-Net, siguiendo la metodología del paper original “Joint Face Detection and Alignment using Multi-task Cascaded Convolutional Networks”.

El trabajo se centra en:

Entrenamiento de P-Net con Keras/TensorFlow.

Generación de propuestas mediante pirámide multiescala.

Aplicación de Supresión No Máxima (NMS).

Análisis de IoU frente a anotaciones reales (WIDER FACE_SELECTED).

| Clase     | Condición IoU   |
| --------- | --------------- |
| Positivo  | IoU ≥ 0.5       |
| Part face | 0.3 ≤ IoU < 0.5 |
| Negativo  | IoU < 0.3       |


Etiquetado supervisado de propuestas para R-Net.

Guardado seguro y reanudable por imagen.

R-Net no se entrena en este proyecto.
El resultado final es un dataset listo para ser usado por R-Net.

# DATASET
WIDER FACE (subset: WIDER_SELECTED)

WIDER_SELECTED/
├── train/
│   ├── 0--Parade/
│   ├── 1--Handshaking/
│   └── ...
├── annotations.txt

# Anexos
checkpoints_pnet-20260114T173419Z-1-001: Contiene los checkpoints de entrenamiento de 15 epocas
rnet_proposals-20260114T173329Z-1-001: Contiene el post procesamiento de 10 imagenes
imagenes_analizadas: Contiene las dos imágenes que se muestran en código con las cajas candidatas.
requirements: Contiene la lista de las dependencias de Python.