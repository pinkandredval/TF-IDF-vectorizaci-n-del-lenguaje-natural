# Taller de Procesamiento de Lenguaje Natural (NLP): TF-IDF en Python

**Valentina Muñoz Palma**

este repositorio realiza el taller parctico de **Analisis de Lenguaje Natural (NLP)** utilizando python en google colab. donde se busca comprender y aplicar el algoritmo **TF-IDF** para la identificacion de palabras discrimiativas dentro del corpus.

## Descripción del Proyecto

el taller contiene el procesamiento de un corpus de documentos con tres categorias: **Deportes, Economía y Tecnología** 

## Fases del Pipeline de NLP

1. **Carga del Corpus:** Importacion y lectura de los documentos dentro de un entorno de Google Colab.
2. **Preprocesamiento y Limpieza:**
   * Tokenizacion mediante Regex.
   * Filtrado de *stop words* (conectores, articulos y preposiciones).
   * Manejo de ruido de caracteres generado por la eliminación de tildes y caracteres especiales.
3. **Analisis de Frecuencias (TF Crudo):** Exploracion inicial de la repeticion de palabras por documento.
4. **Modelado Estadistico (TF-IDF):** Implementación manual y conceptual del balance entre TF e IDF para extraer caracteristicas predictivas optimas.

## Aprendizajes Clave

* **Reduccion de Dimensionalidad:** La eliminación de *stop words* y caracteres vacios reduce drasticamente el tamaño de la matriz de datos y optimiza el costo computacional.
* **Normalizacion:** La necesidad de utilizar variantes logaritmicas o frecuencias relativas para poder escalar la dimension de las variables y poder comparar diferentes documentos.
* **Poder Discriminatorio:** Cómo TF-IDF logra deprimir el peso de terminos transversales o ruidos del lenguaje (como letras sueltas `"n"`, `"s"`, `"pa"`) y promover palabras de alto valor semantico (como `"pensional"`, `"anthropic"`, `"minuto"`).
* **Limitaciones de los Modelos:** Identificacion de las limitaciones de TF-IDF frente a sinonimos y la ambigüedad del contexto.

## Tecnologias Utilizadas

* **Python 3**
* **Google Colab**
* **Pandas** (Estructuración de datos)
* **Regex / Math / Defaultdict** (Procesamiento y cálculo manual)

## Reflexion final

El problema que **TF-IDF** vino a solucionar es la incapacidad de identificar el verdadero peso de las palabras a partir unicamente del conteo de las palabras. esto lo resuelve en tres pasos:
* Primero identifica si la palabra se repite mucho dentro del documento, si es asi le asigna un peso alto porque la palabra describe bien el documento.
* Segundo revisa si la palabra se repite mucho dentro del corpus, si es asi le da un peso cercano a 0 porque esto significa que esa palabra no me ayuda a identificar de que trata cada documento por lo tanto la toma como palabra sin significado o irrelevante.
* Por ultimo hace un producto entre estos para que si existe algun factor cercano a cero o pequeño le de un peso final bajo o nulo y si tiene un peso total alto le de mas importancia a esa palabra.

Me sorprendio la utilidad del procesamiento del lenguaje natural, que a pesar de que se usen diccionarios de palabras vacias muy estandar, las palabras encontradas al final ayudan bastante a identificar el tema principal de los documento.
