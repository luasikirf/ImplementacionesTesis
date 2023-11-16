# Implementaciones del tradajo de Tesis "Estudio De Metaheurísticas Aplicadas A Clustering Para Su Comparación En Distintos Escenarios"
Este repositorio guarda los códigos utilizados en el trabajo de tesis, todos fueron escritos en Python 3, se crearon en [Google Colab](https://colab.research.google.com) por lo cual no hay requisitos mínimos de hardware para su ejecución, cualquier dispositivo con acceso a internet podría ejecutarlos en línea.

## Librerias necesarias
### Necesitan instalación
- [numpy](https://numpy.org/)    `pip install numpy` 
- [pandas](https://pandas.pydata.org/docs/) `pip install pandas`
- [sklearn](https://scikit-learn.org/stable/) `pip install -U scikit-learn`
- [scipy](https://scipy.org/) `python -m pip install scipy`
### Incluidas en Python
- [pickle](https://docs.python.org/3/library/pickle.html) 
- [copy](https://docs.python.org/es/3/library/copy.html) 
- [random](https://docs.python.org/es/3/library/random.html) 
## Ejecutar
### En computadora personal
* Instalar Python.
* Instalar las librerias necesarias no incluidas en python.
* Descargar y abrir el archivo .ipynb que se quiere ejecutar.
* Ejecutar todas las celdas, en una celda nueva llamar la función principal con los parametros deseados. (Ejemplos)
### En [Google Colab](https://colab.research.google.com)
* Descargar y abrir el archivo .ipynb que se quiere ejecutar.
* Ejecutar todas las celdas, en una celda nueva llamar la función principal con los parametros deseados. (Ejemplos)
### Ejemplos ejecución
- [ACDE](/ACDE_EvolucionDiferencial.ipynb)
  La función que vamos a llamar es la siguiente:
  ```
  acde(cr_max: float,cr_min: float,tPoblacion: int,
         k_max: int,x_min: float,x_max: float,nLlamadas: int,
         datos, index='cs')
  ```
  La descripción de la función de cada parámetro se encuentra en el código. Los parámetros $x_{min}$ , $x_{max}$ y $datos$ varían dependiendo el conjunto de datos. Se anexaron los valores de dichas variables en la carpeta [parámetros](/ParametrosDatos), para recuperarlos basta con correr una celda nueva con el siguiente código, en el cual reemplazamos $archivo$ por la ruta de los parametros que queremos.
   ```
  with open(archivo, "rb") as f:
      datos,x_min,x_max = pickle.load(f)
  ```
  
  Se realizaron 2 pruebas en la tesis, una con el parámetro $index =$'cs' y la otra con $index =$'DB', en ambos casos se usaron los siguientes parámetros: 

   `
  cr_max = 1,
  cr_min = 0.5,
  tPoblacion = 10,
  k_max = 20,
  nLlamadas = 100000
  `
  - Ejecutar ACDE en el conjunto [iris]()  
    Una vez que corrimos todas las celdas de la libreta hacemos lo siguiente.
    - Obtenemos los parámetros $x_{min}$ , $x_{max}$ y $datos$ ejecutando en una celda nueva el siguiente código:
    ```
    with open(ruta/ParametrosIris.pickle, "rb") as f:
        iris_datos,iris_min,iris_max = pickle.load(f)
    ```
    **nota: debemos cambiar "ruta" por la dirección donde descargamos el archivo ParametrosIris.pickle**
    - Llamamos la función principal con los parámetros que obtuvimos, podemos cambiar los valores de
      `
      cr_max, cr_min, tPoblacion, k_max, nLlamadas, index
      `, pero para este ejemplo usaremos los mismos valores que en la tesis, quedando del siguiente modo la siguiente celda a ejecutar:

    ```
    acde(cr_max = 1,cr_min = 0.5,tPoblacion = 10,
           k_max = 20,x_min = iris_min ,x_max = iris_max ,nLlamadas: int,
           datos = iris_datos, index='cs')
    ```
     **nota: lo anterior nos devuele la puntuación de **
  - 

- [PSO-Kmeans](/PSO-kmeans.ipynb)
-       hbascihbcfhas
  
- [SAGMDE](SAGMDErecocido.ipynb)
