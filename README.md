# Implementaci-n-de-un-modelo-de-deep-learning




Los modelos y los datos se encontraran en un link de descarga externo. Los links de descarga estan en un documento que se encuentra en este mismo repositorio.
Este README proporciona una descripción del código que crea y mejora dos redes neuronales para la clasificación de cartas. 

## Descripción de dataSet
Las carpetas de data set tienen imágenes de 200 X 200 X 3 en formato jpg. Todas las imágenes en el conjunto de datos han sido recortadas de manera que solo la imagen de una sola carta esté presente y la carta ocupe más del 50% de los píxeles en la imagen. Hay 7624 imágenes de entrenamiento, 265 imágenes de prueba y 265 imágenes de validación. Los directorios de entrenamiento, prueba y validación se dividen en 53 subdirectorios, uno para cada uno de los 53 tipos de cartas. El conjunto de datos también incluye un archivo CSV que se puede utilizar para cargar los conjuntos de datos.

# README para Clasificación de Imágenes de Cartas con Aprendizaje Profundo

Este README proporciona una descripción general del código en Python utilizado para crear y entrenar dos redes neuronales para la clasificación de imágenes de cartas. El código aprovecha el poder del aprendizaje profundo y la transferencia de conocimientos para clasificar imágenes de cartas de juego en diferentes categorías. A continuación, se presenta un desglose de los componentes clave del código y su funcionalidad.


1. Modelo Inicial: Utiliza el modelo preentrenado VGG16 con ajustes finos.
2. Modelo Mejorado: Utiliza el modelo preentrenado EfficientNetB3 con capas personalizadas y técnicas de regularización.

## Estructura del Código

El código está estructurado en varias secciones, cada una con un propósito específico.

1. **Importaciones y Montaje de Google Drive**:
   - Importa las bibliotecas necesarias y monta Google Drive para acceder al conjunto de datos.

2. **Separación y Preprocesamiento de Datos**:
   - Separa el conjunto de datos en conjuntos de entrenamiento, prueba y validación.
   - Utiliza `ImageDataGenerator` para aumentar los datos, escalar y aplicar otras transformaciones.

3. **Transferencia de Aprendizaje con VGG16 (Modelo Inicial)**:
   - Carga el modelo VGG16 preentrenado con pesos de ImageNet.
   - Excluye la capa superior y lo configura para el tamaño de entrada dado.
   - Establece las capas de VGG16 como no entrenables.
   - Define la arquitectura del modelo agregando capas personalizadas.
   - Compila el modelo utilizando el optimizador Adam y la pérdida de entropía cruzada categórica.
   - Entrena el modelo con los datos de entrenamiento y lo valida utilizando el conjunto de validación.

4. **Evaluación del Modelo (Modelo Inicial)**:
   - Evalúa el rendimiento del modelo inicial en el conjunto de datos de prueba.

5. **Predicciones Personalizadas para los Usuarios (Modelo Inicial)**:
   - Permite a los usuarios ingresar imágenes de cartas personalizadas y predecir sus clases.

6. **Modelo Mejorado con EfficientNetB3**:
   - Carga el modelo EfficientNetB3 preentrenado con pesos de ImageNet.
   - Define la arquitectura con capas personalizadas, incluyendo dropout y técnicas de regularización.
   - Compila el modelo utilizando el optimizador Adamax y la pérdida de entropía cruzada categórica.
   - Entrena el modelo mejorado con los datos de entrenamiento y lo valida utilizando el conjunto de validación.

7. **Evaluación del Modelo (Modelo Mejorado)**:
   - Evalúa el rendimiento del modelo mejorado en el conjunto de datos de prueba.

8. **Predicciones Personalizadas para los Usuarios (Modelo Mejorado)**:
   - Permite a los usuarios ingresar imágenes personalizadas de cartas y predecir sus clases.

## Ejecución del Código

1. Asegúrate de tener las bibliotecas necesarias instaladas. Puedes instalarlas con `pip install` si es necesario.

2. Carga el código en un cuaderno de Jupyter, preferiblemente en Google Colab.

3. Monta tu Google Drive para acceder al conjunto de datos almacenado en el directorio especificado.

4. Ejecuta las secciones del código paso a paso, siguiendo los comentarios y explicaciones proporcionadas.

5. Puedes elegir ejecutar el modelo inicial o el modelo mejorado comentando o descomentando las secciones de código relevantes.

6. Evalúa el rendimiento del modelo en el conjunto de datos de prueba.

7. Prueba predicciones personalizadas de imágenes de cartas cargadas utilizando el modelo entrenado.

## Archivos de Modelo

Los modelos entrenados se guardarán como archivos `.h5`. Puedes descargarlos para utilizarlos en tus tareas de clasificación de imágenes de cartas.

## Nota

- El modelo inicial logra una precisión de aproximadamente el 74%.
- El modelo mejorado logra una precisión de aproximadamente el 95%.
