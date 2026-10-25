# Entrega 3 - Evolución del clasificador de especies vegetales

**Trabajo Práctico Integral de Inteligencia Artificial Avanzada - UTN FRBA - Grupo C.**

## Objetivo

Evaluar técnicas de preprocesamiento, Transfer Learning y fine-tuning para mejorar el clasificador desarrollado en Entrega 2. El sistema identifica una de ocho especies y obtiene su condición Nativa/Exótica mediante el catálogo regional de la Provincia de Buenos Aires.

Las corridas utilizan 3.200 imágenes de iNaturalist, distribuidas en 1.920 de entrenamiento, 480 de validación y 800 de test, con entrada RGB de 224 x 224 píxeles.

## Experimentos

| Experimento | Configuración |
|---|---|
| [4](notebooks/04_Exp4_ObjectDetectionCrop_CNN_GAP.ipynb) | Recortes propuestos por un detector preentrenado y CNN con GlobalAveragePooling2D. |
| [4B](notebooks/04B_Exp4_ObjectDetectionCrop_CNN_GAP.ipynb) | Detección y CNN GAP con tasa de aprendizaje adaptable. |
| [4C](notebooks/04C_Exp4_ObjectDetectionCrop_CNN_GAP.ipynb) | CNN GAP con tasa adaptable sobre imágenes completas. |
| [5](notebooks/05_Exp5_TransferLearning_MobileNetV2.ipynb) | MobileNetV2 preentrenada, con extractor congelado y entrenamiento del clasificador. |
| [6](notebooks/06_Exp6_FineTuning_MobileNetV2.ipynb) | Fine-tuning desde `block_16_expand`, con BatchNormalization congelada. |
| [7](notebooks/07_Exp7_FineTuning_MobileNetV2_block15.ipynb) | Fine-tuning desde `block_15_expand`. |
| [8](notebooks/08_Exp8_FineTuning_MobileNetV2_AugmentationSuave.ipynb) | Fine-tuning desde `block_16_expand` con augmentation suave. |

## Prototipo final

Se seleccionó el **Experimento 8**, que trabaja sobre imágenes completas y aplica reflexión horizontal y rotación suave únicamente durante el entrenamiento. La selección se basa en la menor pérdida de validación, **0,7122**, recuperando los pesos de la época **22** de las 34 ejecutadas.

Resultados del prototipo en el conjunto de **test, n=800**:

| Métrica | Resultado |
|---|---:|
| Accuracy por especie | 77,25 % |
| Macro-F1 por especie | 77,25 % |
| Pérdida de test | 0,7044 |
| Accuracy Nativa/Exótica | 85,63 % |
| Macro-F1 Nativa/Exótica | 85,62 % |

[Resultados del prototipo final](resultados/08_Exp8_FineTuning_MobileNetV2_AugmentationSuave/)

## Archivos

- [notebooks/](notebooks/): cuadernos de los experimentos para Google Colab.
- [resultados/](resultados/): métricas, predicciones, historiales, reportes por clase, manifiestos, curvas y matrices de confusión por corrida.
- [Informe en PDF](informe/IA_Avanzada_GrupoC_Entrega3.pdf): versión para la entrega, con desarrollo, comparación de experimentos y conclusiones.

Los experimentos 4, 4C y 5 a 8 comparten las mismas observaciones, fotografías y particiones. El 4B utiliza otra selección y partición, por lo que su comparación es exploratoria. La comparación con Entrega 2 es descriptiva: no se certificó que sus imágenes de test sean idénticas. El test fue consultado durante el desarrollo y no constituye una evaluación externa nunca observada.

## Ejecución

Abrir el notebook en Google Colab, seleccionar un entorno con GPU y ejecutar las celdas en orden. Configurar las rutas de Drive y conservar las imágenes originales en `dataset_raw`.

Los experimentos 6, 7 y 8 requieren los archivos originales del Experimento 5: `modelo_exp5.keras`, `metricas_entrega3_exp5.json` y `manifest_splits.csv`. Los tres están incluidos en [resultados/05_TransferLearning_MobileNetV2/](resultados/05_TransferLearning_MobileNetV2/). Copiarlos juntos a la carpeta de Drive indicada por `SOURCE_DIR` (por defecto, `MyDrive/2026_IAA_GrupoC`). Los notebooks verifican el modelo, las particiones y el orden de clases; no deben mezclarse archivos de otras corridas.

Los resultados se exportan a `artifacts_entrega3/runs`; las imágenes de trabajo se preparan en el almacenamiento temporal de Colab. El guardado del modelo `.keras` es opcional y permanece comentado en el bloque de exportación.

El repositorio incluye los resultados de la corrida final del Experimento 8, pero no sus pesos. Para hacer inferencia con ese checkpoint exacto se necesita su modelo guardado; volver a entrenar puede producir resultados diferentes. Para conservar un nuevo modelo, descomentar su guardado después de restaurar los mejores pesos.

[Volver al proyecto](../README.md)
