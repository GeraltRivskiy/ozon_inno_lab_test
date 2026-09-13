# Barcode dataset for YOLO

InventBar and ParcelBar объединены в один датасет для задачи детекции штрихкодов. Исходное разделение по источникам не используется при обучении.

## Структура

```text
dataset/
├── data.yaml
├── images/
│   ├── train/  # 1 097 изображений
│   ├── val/    #   137 изображений
│   └── test/   #   137 изображений
└── labels/
    ├── train/  # 1 097 YOLO-аннотаций
    ├── val/    #   137 YOLO-аннотаций
    └── test/   #   137 YOLO-аннотаций
```

Всего: 1 371 изображение, 1 615 bounding boxes, один класс — `barcode` (ID `0`). Разбиение выполнено с фиксированным seed `42`: 80% / 10% / 10%. В каждом сплите сохранена пропорция исходных InventBar и ParcelBar.

Для обучения Ultralytics YOLO используйте конфигурацию [`data.yaml`](data.yaml):

```bash
yolo detect train data=task_2/dataset/data.yaml model=yolo11n.pt epochs=100 imgsz=640
```

## Источник

InventBar and ParcelBar-1D Barcode Detection: Novel Benchmark Datasets and Comprehensive Comparison of Deep Convolutional Neural Network Approaches.

Kamnardsiri, T., Charoenkwan, P., Malang, C., & Wudhikarn, R. (2022). *1D barcode detection: Novel benchmark datasets and comprehensive comparison of deep convolutional neural network approaches*. Sensors, 22(22), 8788.
