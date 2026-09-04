# Inteligencia Artificial Avanzada — Grupo C

Repositorio correspondiente al Trabajo Práctico Integral de **Inteligencia Artificial Avanzada — UTN FRBA**.

El proyecto aborda la **identificación automática de especies vegetales a partir de imágenes** mediante técnicas de Inteligencia Artificial y su posterior clasificación regional como **Nativa o Exótica en la Provincia de Buenos Aires**.

La solución se organiza en entregas incrementales. Cada etapa parte de los resultados obtenidos previamente e incorpora nuevas técnicas, experimentos y mejoras sobre el prototipo.

---

## Estructura del repositorio

```text
.
├── Entrega_2/
│   ├── informe/
│   ├── notebooks/
│   ├── dataset/
│   └── README.md
│
└── Entrega_3/
    └── ...
```

Cada carpeta contiene los archivos correspondientes a una entrega específica del Trabajo Práctico.

---

## Entrega 2 — Prototipo de clasificación mediante CNN

La **Entrega 2** desarrolla una prueba de concepto para identificar una de ocho especies vegetales mediante Redes Neuronales Convolucionales.

Se evaluaron tres configuraciones sobre el mismo dataset y la misma partición de entrenamiento, validación y prueba:

1. **CNN con Flatten**
   - Utilizada como línea base.
   - Presentó un marcado sobreajuste.

2. **CNN con GlobalAveragePooling2D**
   - Redujo significativamente la cantidad de parámetros entrenables.
   - Obtuvo el mejor desempeño sobre el conjunto de prueba.
   - Fue seleccionada como prototipo final de la Entrega 2.

3. **CNN con GlobalAveragePooling2D + Data Augmentation**
   - Incorporó transformaciones aleatorias durante el entrenamiento.
   - Redujo la brecha entre entrenamiento y validación.
   - No superó al Experimento 2 sobre el conjunto de prueba.

La Entrega 2 incluye:

- notebooks correspondientes a los tres experimentos;
- manifest y documentación del dataset;
- resultados y métricas de evaluación incluidos en los notebooks;
- informe final de la entrega.

➡️ Ver [`Entrega_2/`](./Entrega_2/)

---

## Entrega 3 — Evolución del sistema

La carpeta **Entrega_3** contendrá la evolución del prototipo desarrollado en la Entrega 2.

Las mejoras serán definidas a partir de los resultados y limitaciones detectadas en la etapa anterior, incorporando nuevas técnicas y comparando su desempeño contra el prototipo seleccionado.

➡️ Ver [`Entrega_3/`](./Entrega_3/)

---

## Flujo general del sistema

```text
Imagen de una planta
        ↓
Modelo de Inteligencia Artificial
        ↓
Identificación de especie
        ↓
Consulta de catálogo botánico regional
        ↓
Nativa / Exótica
```

La condición regional no se infiere directamente a partir de la imagen.

El modelo identifica la especie y posteriormente se consulta un catálogo botánico para determinar su condición en la Provincia de Buenos Aires.

---

## Integrantes — Grupo C

- Guido Julián Martinez
- Gonzalo Duarte
- Tomás Esteban Gliozzo
- Camila Lazzati
- Fidel Ibire
- Federico Ascorti

---

## Tecnologías utilizadas

- Python
- Google Colab
- TensorFlow / Keras
- Pandas
- Scikit-learn
- Matplotlib
- Pillow
- iNaturalist API

---

## Organización por entregas

Cada entrega posee su propio `README.md` con información específica sobre:

- objetivo;
- metodología;
- experimentos realizados;
- dataset utilizado;
- resultados;
- notebooks asociados;
- informe correspondiente.

El objetivo de este README raíz es mantener una visión general del proyecto y facilitar la navegación entre las distintas etapas del Trabajo Práctico.
