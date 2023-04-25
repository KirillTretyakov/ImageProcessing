# Практическая работа 3
## Классификации объектов на изображении в среде Python, используя алгоритм кластеризации методом К-средних (Режим обучения: Без учителя)
### Шаг 1. Сжать исходное изображение используя метод K-means, встроенный в библиотеку Scikit-learn при следующих вариантах количества цветов: 2, 3, 4, 8, 16, 32, 64, 128, 256. Сохранить получившиеся изображения в отдельную папку (Scikit Compressor) и продемонстрировать их в отчёте.

1. Импортируем библиотеки, а также запускаем функцию для дальнейшего игнорирования предупреждений (чтобы они не показывались)
```
from sklearn.cluster import KMeans
import cv2
import numpy as np
import imutils
import time
import os
import numpy as np
import matplotlib
from PIL import Image
import warnings
warnings.filterwarnings("ignore")
```
2. Задаем список из разного количества цветов, кладём в переменную наше изображение, нормализуем его
```
palette = [1,2,3,4,8,16,32,64,128,256]
img = cv2.imread('Bears.jpg')
img_r = (img / 255.0).reshape(-1,3)
```
3. Проходимся циклом по всем цветам, и применяем к ним сжатие методом k-means, затем сохраняем их
Результат:
![](/ScikitCompressor/bears_1_palette.jpg)
!(/ScikitCompressor/bears_2_palette.jpg)
!(/ScikitCompressor/bears_3_palette.jpg)
!(/ScikitCompressor/bears_4_palette.jpg)
!(/ScikitCompressor/bears_8_palette.jpg)
!(/ScikitCompressor/bears_16_palette.jpg)
!(/ScikitCompressor/bears_32_palette.jpg)
!(/ScikitCompressor/bears_64_palette.jpg)
!(/ScikitCompressor/bears_128_palette.jpg)
!(/ScikitCompressor/bears_258_palette.jpg)
