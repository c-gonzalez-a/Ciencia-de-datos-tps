# Ciencia de Datos - Trabajos Practicos

Repositorio con las entregas del Grupo 01 para dos trabajos practicos de ciencia de datos. El contenido esta organizado en dos carpetas principales:

- TP1: clasificacion sobre reservas hoteleras.
- TP2: analisis de sentimiento sobre criticas cinematograficas en espanol.

## Contenido del repositorio

### TP1 - Reservas de Hotel

Trabajo enfocado en predecir cancelaciones de reservas hoteleras a partir de variables tabulares como tipo de hotel, anticipacion de la reserva, canal de distribucion, ADR, pedidos especiales y datos historicos del cliente.

Incluye:

- notebooks por checkpoint para mostrar la evolucion del analisis y los modelos;
- datasets y modelos (no versionados en este repo para mantenerlo liviano);
- predicciones y submissions exportadas;
- ensambles basados en Voting y Stacking, ademas de modelos como Decision Tree, Random Forest y XGBoost.

Archivos principales:

- `TP1/checkpoint 1/7506R_TP1_GRUPO01_CHPX_ENTREGA.ipynb`
- `TP1/checkpoint 2/7506R_TP1_GRUPO01_CHP2_ENTREGA.ipynb`
- `TP1/checkpoint 3/7506R_TP1_GRUPO01_CHP3_ENTREGA.ipynb`
- `TP1/checkpoint 4/7506R_TP1_GRUPO01_CHP4_ENTREGA.ipynb`
- `TP1/predicts/`

Variable objetivo:

- `is_canceled`

### TP2 - Criticas Cinematograficas

Trabajo orientado a clasificacion de sentimiento en resenas de peliculas en espanol. El dataset contiene textos en la columna `review_es` y la etiqueta objetivo en `sentimiento`.

Incluye:

- notebook final de entrega;
- versiones preprocesadas del dataset (descarga externa);
- listas de stopwords en espanol e ingles;
- modelos clasicos de NLP con representaciones vectoriales;
- experimentos con SVM, Naive Bayes, Random Forest, XGBoost, redes recurrentes LSTM/GRU y un baseline con pysentimiento;
- multiples archivos de submission generados durante la experimentacion.

Archivos principales:

- `TP2/7506R_TP2_GRUPO01_ENTREGA.ipynb`
- `TP2/submissions/`
- `TP2/stopwords/`

Variables principales:

- `review_es`: texto de la critica.
- `sentimiento`: clase objetivo.

## Estructura

```text
.
|-- README.md
|-- TP1/
|   |-- requirements.txt
|   |-- checkpoint 1/
|   |-- checkpoint 2/
|   |-- checkpoint 3/
|   |-- checkpoint 4/
|   |-- datasets/
|   |-- models/
|   `-- predicts/
`-- TP2/
	|-- requirements.txt
	|-- torch-cuda-118.txt
	|-- datasets/
	|-- models/
	|-- stopwords/
	`-- submissions/
```

## Requisitos

El proyecto usa Python y notebooks de Jupyter. Las dependencias estan separadas por trabajo practico.

Dependencias base de TP1:

- pandas
- numpy
- seaborn
- scikit-learn
- graphviz
- xgboost
- plotly
- joblib

Dependencias adicionales de TP2:

- nltk
- langdetect

Tambien se incluye un archivo opcional para instalar PyTorch con CUDA 11.8:

- `TP2/torch-cuda-118.txt`

## Instalacion

Se recomienda crear un entorno virtual y luego instalar dependencias por separado segun el trabajo practico que se quiera ejecutar.

### Windows PowerShell

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r .\TP1\requirements.txt
pip install -r .\TP2\requirements.txt
```

### Linux / macOS

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r ./TP1/requirements.txt
pip install -r ./TP2/requirements.txt
```

Si se quiere ejecutar la parte de redes neuronales de TP2 con GPU compatible:

```powershell
pip install -r .\TP2\torch-cuda-118.txt
```

## Como ejecutar

1. Abrir el repositorio en VS Code o Jupyter Lab.
2. Instalar las dependencias del trabajo practico correspondiente.
3. Abrir el notebook deseado.
4. Ejecutar las celdas en orden.

Sugerencia:

- para TP1 conviene empezar por el checkpoint mas avanzado si solo interesa reproducir la entrega final;
- para TP2 conviene usar el notebook principal y revisar la carpeta `submissions/` para comparar resultados ya exportados.

## Modelos y artefactos

El repositorio ya incluye parte de los artefactos generados durante la cursada:

- predicciones de TP1 en `TP1/predicts/`;
- submissions de TP2 en `TP2/submissions/`;
- notebooks, scripts y configuraciones para volver a entrenar modelos.

Para mantener el repositorio liviano, los datasets y modelos pesados no se versionan en Git.

### Modelo externo de TP2

Uno de los modelos de red neuronal no esta versionado en el repositorio y debe descargarse aparte:

- URL: https://drive.google.com/file/d/10hzlVolmhI07uvy5yzz4LIw1--3K9oN2/view?usp=sharing
- destino: extraer el contenido dentro de `TP2/models/`

## Notas

- Algunos notebooks guardan salidas extensas y resultados intermedios de entrenamiento.
- Hay multiples archivos de salida porque el repositorio conserva distintas corridas y variantes de modelos.
- Para reproducir exactamente ciertos experimentos puede ser necesario contar con los mismos artefactos o modelos previamente entrenados.
