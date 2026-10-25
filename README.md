# Inteligencia Artificial Avanzada - Grupo C

Trabajo Práctico Integral de **Inteligencia Artificial Avanzada, UTN FRBA**.

## Objetivo

Identificar una de ocho especies vegetales a partir de una fotografía y consultar un catálogo botánico para informar su condición como **Nativa o Exótica en la Provincia de Buenos Aires**.

`Imagen RGB -> Clasificación de especie -> Catálogo regional -> Nativa / Exótica`

El proyecto utiliza imágenes de iNaturalist y evoluciona desde redes convolucionales entrenadas desde cero hasta modelos preentrenados con ajuste fino.

## Entrega 2: clasificación mediante CNN

Se evaluaron tres configuraciones: CNN con Flatten, CNN con GlobalAveragePooling2D y CNN con Data Augmentation. Se trabajó con 3.200 imágenes de ocho especies.

El **Experimento 2, CNN con GlobalAveragePooling2D**, fue seleccionado como prototipo de esta etapa, con **61,12 % de accuracy y 59,75 % de macro-F1 por especie en test**.

[Descripción de Entrega 2](Entrega_2/README.md) | [Informe](Entrega_2/informe/IA_Avanzada_GrupoC_Entrega2.pdf) | [Notebooks](Entrega_2/notebooks/)

## Entrega 3: evolución del prototipo

Se exploraron recortes con Object Detection, tasa de aprendizaje adaptable, Transfer Learning con MobileNetV2, fine-tuning y augmentation suave.

La versión final es el **Experimento 8, MobileNetV2 con fine-tuning parcial y augmentation suave**, seleccionado por su menor pérdida de validación. Obtuvo **77,25 % de accuracy y 77,25 % de macro-F1 por especie en test**.

[Descripción de Entrega 3](Entrega_3/README.md) | [Informe](Entrega_3/informe/IA_Avanzada_GrupoC_Entrega3.pdf) | [Notebooks](Entrega_3/notebooks/) | [Resultados](Entrega_3/resultados/)

## Contenido del repositorio

| Carpeta | Contenido |
|---|---|
| [Entrega_2](Entrega_2/) | Informe, tres notebooks y documentación del dataset. |
| [Entrega_3](Entrega_3/) | Informe, siete notebooks y resultados por experimento. |

## Tecnologías

Python, Google Colab, TensorFlow/Keras, Scikit-learn, Pandas, NumPy, Matplotlib, Pillow y API de iNaturalist.

## Integrantes

- Guido Julián Martinez
- Gonzalo Duarte
- Tomás Esteban Gliozzo
- Camila Lazzati
- Fidel Ibire
- Federico Ascorti
