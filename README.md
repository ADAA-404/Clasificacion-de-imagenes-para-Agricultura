# Clasificacion-de-imagenes-para-Agricultura 🌱
Este proyecto tiene como objetivo desarrollar un modelo de clasificación para la segmentación semántica de imágenes aéreas en el contexto agrícola. El problema principal que resuelve es la identificación y clasificación automática de diferentes tipos de cobertura y uso del suelo (clases de tierra) a partir de imágenes, lo cual es fundamental para el monitoreo de cultivos, gestión de recursos hídricos, planificación del uso del suelo y agricultura de precisión. Se entrena un clasificador de Regresión Logística para predecir la clase de cada píxel, creando una máscara de segmentación.


## Tecnologias usadas 🐍
- pandas: Para manipulación y estructuración de datos tabulares (creación del DataSet a partir de los píxeles de las imágenes).
- numpy: Para operaciones numéricas eficientes, especialmente con arreglos de píxeles de imágenes.
- matplotlib: Para la visualización de imágenes y gráficos de datos.
- seaborn: Para la visualización estadística y de conteo de clases.
- scikit-learn (sklearn): Para la implementación del modelo de clasificación (LogisticRegression) y la evaluación del mismo (ConfusionMatrixDisplay, accuracy_score).
- Pillow (PIL): Para la apertura y manipulación de imágenes (Image).
- opencv (cv2): Utilizado para operaciones de procesamiento de imágenes.
- colormap: Para la conversión de colores RGB a HEX y viceversa, fundamental para la manipulación de las máscaras de segmentación.
- os y glob: Para la navegación y listado de archivos en el sistema de directorios.
- json: Para la lectura de archivos de configuración de clases.
- skillsnetwork: Una librería específica para la descarga de datos de IBM Cloud.


## Consideraciones en Instalación ⚙️
Para configurar y ejecutar el proyecto, necesitas algunas librerías de Python que son importantes instalarlas en el entorno a usar; en este caso se usa 'conda'

conda install -y matplotlib scikit-learn seaborn pandas numpy pillow

conda install -c conda-forge -y opencv colormap
conda install -c intel -y scikit-learn

pip install skillsnetwork

En el codigo se utiliza un comando 'await skillsnetwork.prepare(...)' que descarga y descomprime el conjunto de datos de imágenes. Este comando debe ejecutarse en un entorno que soporte 'await' (como un Jupyter Notebook o IPython).

## Ejemplo de uso 📎
Este codigo realiza una serie de pasos para clasificar píxeles de imágenes agrícolas, siguiendo este flujo de ejecución:
 1. Descarga y Carga de Datos de Imagen: se comienza descargando un conjunto de datos (usamos IBM Cloud para este caso) donde la función 'get_data' procesa los archivos 'classes.json' y carga las imágenes.
 2. Creación del Conjunto de Datos (DataSet): la función create_DataSet transforma las imágenes y sus máscaras en un DataFrame de pandas, cada fila representa un píxel con sus respectivas propiedades.
 3. Visualización de la Distribución de Clases: se utilizan gráficos de barras para visualizar la distribución de las clases (representadas por valores HEX de color) en los conjuntos de datos de entrenamiento y prueba.
 4. Entrenamiento y Evaluación del Clasificador: se entrena un modelo de Regresión Logística utilizando los valores RGB de la imagen original como características para predecir la clase HEX.
 5. Segmentación de Imagen de Prueba y Visualización: finalmente, el modelo entrenado se utiliza para predecir la clase de píxeles en una nueva imagen de prueba.

## NOTA ⚠️
Este proyecto tiene 2 métodos por los cuales se puede compilar, depende de donde y como se quiera evaluar; esto recae en la obtención de la base datos, una considera un acceso mediante Jupyter Notebook (o parecidos) y otra en consultas tradicionales para usar en scripts.
Se adjuntan los dos archivos para probar, la version 2 es el codigo con el metodo manual para consultar las bases de datos.

## Contribuciones 🖨️
Si te interesa contribuir a este proyecto o usarlo independiente, considera:
- Hacer un "fork" del repositorio.
- Crear una nueva rama (git checkout -b feature/nueva-caracteristica).
- Realizar tus cambios y "commitearlos" (git commit -am 'Agregar nueva característica').
- Subir tus cambios a la rama (git push origin feature/nueva-caracteristica).
- Abrir un "Pull Request".


## Licencia 📜
Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE (si aplica) para más detalles.
