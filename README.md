# Identificador de Objetos Inteligente con Teachable Machine y TensorflowJS

## Descripción

Este proyecto consiste en una aplicación web que integra un modelo de Machine Learning entrenado con **Google Teachable Machine** para clasificar objetos en tiempo real mediante la webcam del usuario. La aplicación utiliza **TensorflowJS**, una biblioteca de JavaScript para ejecutar modelos de ML directamente en el navegador, lo que permite realizar inferencias sin necesidad de servidores o instalaciones adicionales.

El modelo fue entrenado para identificar cinco clases de objetos comunes: **celular, teclado, mouse, lentes y nada** (sin objeto visible). La interfaz es moderna, colorida y dinámica, diseñada para facilitar la experiencia del usuario y mostrar resultados de manera clara y atractiva.

---

## Respuestas a preguntas del enunciado

### ¿Qué es Teachable Machine y cómo se entrena un modelo ahí?

**Teachable Machine** es una herramienta web desarrollada por Google que permite a cualquier persona crear modelos de aprendizaje automático de manera sencilla y sin necesidad de programar. Para entrenar un modelo, el usuario selecciona el tipo (imagen, audio o poses), proporciona ejemplos etiquetados para cada clase (por ejemplo, imágenes de un celular o un mouse), y la plataforma entrena automáticamente un modelo en la nube usando esos datos. Posteriormente, se puede probar, mejorar y finalmente exportar el modelo para su uso en diferentes aplicaciones.

### ¿Cómo se exporta un modelo para uso en web (TensorflowJS)?

Después de entrenar un modelo en Teachable Machine, se puede exportar para uso en aplicaciones web eligiendo la opción de exportar en formato **TensorflowJS**. Esto genera una carpeta que contiene un archivo `model.json` y varios archivos `.bin` con los pesos y arquitectura del modelo. Estos archivos son los que luego se cargan directamente desde la web usando la librería TensorflowJS para ejecutar predicciones en el navegador.

### ¿Qué es TensorflowJS y cómo se utiliza para cargar un modelo?

**TensorflowJS** es una biblioteca de JavaScript que permite ejecutar modelos de Machine Learning directamente en el navegador web o en Node.js. Para cargar un modelo entrenado y exportado para TensorflowJS, se utiliza la función asíncrona `tf.loadLayersModel(url)`, donde `url` es la ruta al archivo `model.json`. Una vez cargado, se pueden enviar datos (imágenes, audio, etc.) para realizar predicciones con la función `model.predict()`.

### Breve explicación de qué es `.h5` y cómo se exporta un modelo en Python (Keras)

El archivo con extensión `.h5` es un formato estándar para almacenar modelos entrenados en Keras, que incluye tanto la arquitectura del modelo como sus pesos entrenados. En Python, después de entrenar un modelo con Keras, se guarda con el método:

```python
model.save('modelo.h5')
