# Inteligencia Artificial Avanzada - Grupo C

## Entrega 2 - Identificación de especies vegetales

Trabajo Práctico Integral de Inteligencia Artificial Avanzada
- UTN FRBA.

## Objetivo 

Desarrollar una prueba de concepto capaz de identificar una
especie vegetal a partir de una fotografía y posteriormente
informar su condición como Nativa o Exótica en la Provincia
de Buenos Aires.

El sistema se estructura en dos etapas:

Imagen → CNN → Especie → Catálogo regional → Nativa / Exótica

## Dataset

Se utilizaron 3.200 imágenes obtenidas desde iNaturalist,
correspondientes a ocho especies.

- Train: 1.920
- Validation: 480
- Test: 800

## Experimentos

### Experimento 1 - CNN con Flatten

Arquitectura utilizada como línea base.

- Parámetros entrenables: 16.871.624
- Test Accuracy: 38,13 %
- Macro-F1: 37,55 %

### Experimento 2 - CNN con GlobalAveragePooling2D

Se reemplazó Flatten por GlobalAveragePooling2D.

- Parámetros entrenables: 110.792
- Test Accuracy: 61,12 %
- Macro-F1: 59,75 %

**Configuración seleccionada como prototipo de la Entrega 2.**

### Experimento 3 - GAP + Data Augmentation

Se incorporaron transformaciones aleatorias durante entrenamiento.

- Test Accuracy: 44,50 %
- Macro-F1: 42,56 %

El Data Augmentation redujo la brecha entre entrenamiento y
validación, pero no mejoró el desempeño sobre test frente
al Experimento 2.

## Estructura

- `notebooks/`: código correspondiente a los tres experimentos.
- `dataset/`: manifest y documentación del dataset.
- `informe/`: informe de la Entrega 2.

## Informe

Ver `informe/IA_Avanzada_GrupoC_Entrega2.pdf`.
