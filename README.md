# Segmentación de la Glotis utilizando YOLOv8 y Unet

## Descripción del Proyecto

Este proyecto se centra en la segmentación de la glotis utilizando modelos de YOLOv8. 
## Datasets

- **BAGLS**: Utilizado para el entrenamiento y evaluación de los modelos YOLOV8(1 clase) y Unet. Puedes descargarlo desde [aquí](https://zenodo.org/record/6938457).
- **LSTM Network - dataset & code**: Utilizado para el entrenamiento de YOLOV8(3 clases). Puedes descargarlo desde [aquí](https://zenodo.org/records/7395763).

## Requerimientos

Para ejecutar este proyecto, asegúrate de tener instaladas las dependedencias del archivo requirements, puedes instalarlas con el comando **pip install -r requirements.txt**

## Distribución de Carpetas y Archivos

### YOLOV8

- `runs/segment/train2/weights`: Contiene los pesos del modelo YOLOv8 entrenado.
  - `best.pt`: Mejor modelo entrenado.
  - `last.pt`: Último modelo entrenado.
- `YoloV8_Train.ipynb`: Código para el entrenamiento del modelo YOLOv8.
- `create_dataset_yolo.ipynb`: Código para modificar el dataset BAGLS al formato YOLO, pasando las máscaras a coordenadas y reorganizando las carpetas.
- `predict_yolov8.ipynb`: Código para utilizar el modelo YOLOv8 con videos y ponerlo a prueba.
- `dataset.yaml`: Configuración del dataset para YOLOv8.
- `yolov8n-seg.pt`: Pesos del modelo YOLOv8 de segmentación.
- `yolov8n.pt`: Pesos del modelo YOLOv8.

### YOLOV8_3cls_seg
- `runs/segment/train2/weights`: Contiene los pesos del modelo YOLOv8 entrenado.
  - `best.pt`: Mejor modelo entrenado.
  - `last.pt`: Último modelo entrenado.
- `train_yolov8_3cls_seg.ipynb`: Código para el entrenamiento del modelo YOLOv8.
- `create_dataset_yolo_3cls_seg.ipynb`: Código para modificar el dataset BAGLS al formato YOLO, pasando las máscaras a coordenadas y reorganizando las carpetas.
- `predict_yolov8_3cls_seg.ipynb`: Código para utilizar el modelo YOLOv8 con videos y ponerlo a prueba.
- `create_dataset_yolo_3cls_seg.ipynb`: Código para modificar el dataset BAGLS al formato YOLO, pasando las máscaras a coordenadas y reorganizando las carpetas, incluye pruebas adicionales para entender el formato del dataset, ya que este dataset contiene 3 clases.

### metrics

- `metrics_iou.ipynb`: Funciones para calcular el IoU entre el modelo Unet y YOLO utilizando el conjunto de datos test de BAGLS.(Incompleto, solo funciona para Unet)
- `model_GlottisNetV2e.csv`: Archivo CSV con los resultados del modelo GlottisNetV2e.
- `results_YOLO.csv`: Archivo CSV con los resultados de entrenamiento del modelo YOLO.
- `results_YOLO_3cls.csv`: Archivo CSV con los resultados de entrenamiento del modelo YOLO para tres clases.
- `train_metrics_yolo.ipynb`: Contiene las gráficas de comparación de los valores de ambos modelos YOLO.
