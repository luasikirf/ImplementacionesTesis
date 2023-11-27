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
* Ejecutar todas las celdas, en una celda nueva llamar la función principal con los parametros deseados. (Ver ejemplos de ejecución.)
### En [Google Colab](https://colab.research.google.com)
* Descargar y abrir el archivo .ipynb que se quiere ejecutar.
* Ejecutar todas las celdas, en una celda nueva llamar la función principal con los parametros deseados. (Ver ejemplos de ejecución.)
### Ejemplos ejecución
Sigue estas indicaciones si quieres usar alguna implementación para clasificar un conjunto de datos y obtener sus etiquetas.


#### [ACDE](/ACDE_EvolucionDiferencial.ipynb)
  Tras ejecutar este código, nos regresa un objeto con las siguientes propiedades:
  * objeto.activos - Lista con los índices de los grupos activos.
  * objeto.aptitud - Puntuación obtenida en la función de aptitud.
  * objeto.fx - Puntuación obtenida en la función objetivo introducida por el usuario.
  * objeto.particion - Lista con el etiquetado asignado a los datos introducidos.
  
La función que vamos a llamar es la siguiente:
  ```
  acde(cr_max: float,cr_min: float,tPoblacion: int,
         k_max: int,x_min,x_max,nLlamadas: int,
         datos, index='cs')
  ```
  La descripción de la función de cada parámetro se encuentra en el código. Los parámetros $x_{min}$ , $x_{max}$ y $datos$ varían dependiendo el conjunto de datos. Se anexaron los valores de dichas variables en la carpeta [parámetros](/ParametrosDatos),para recuperarlos sigue las instrucciones en dicha carpeta.
  
  Se realizaron 2 pruebas en la tesis, una con el parámetro $index =$'cs' y la otra con $index =$'DB', en ambos casos se usaron los siguientes parámetros:
   `
  cr_max = 1,
  cr_min = 0.5,
  tPoblacion = 10,
  k_max = 20,
  nLlamadas = 100000
  `
  - Ejecutar ACDE en el conjunto iris.
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
       **nota: lo anterior nos devuele un objeto, vea sus propiedades al inicio de este ejemplo**

  #### [PSO-Kmeans](/PSO-kmeans.ipynb)
  Tras ejecutar este código obtenemos un objeto, del cual nos interesan las siguientes propiedades:
  * objeto.posicion - Lista con los centroides de los grupos generados.
  * objeto.aptitud - Puntuación obtenida en la función de aptitud.
  * objeto.labels_ - Lista con el etiquetado asignado a los datos introducidos.  
  La función que vamos a llamar es la siguiente:
  ```
  pso(x_min,x_max,v_min: flot,v_max: float ,k: int,
  n_part: int,iter_pso: int,iter_kmean: int,c1: float ,c2: float ,datos,f_apt)

  ```
  [**Puedes ver el significado de cada parámetro en el siguiente readme**]()  
  Los parámetros $x_{min}$ , $x_{max}$, $datos$ y $k$ varían dependiendo el conjunto de datos. Los valores de $x_{min}$ , $x_{max}$ y $datos$ se pueden recuperar con las instrucciones de la carpeta [parámetros](/ParametrosDatos). $k$ es el número de grupos a formar, la cantidad de grupos que contienen los datos.  
  
  En el trabajo de tesis utilizamos 2 funciones aptitud diferentes, en ambos casos, los parámetros que no cambian tuvieron los siguientes valores:
  `
  v_min = 0,
  v_max = 1,
  n_part= 10,
  iter_pso=800,
  iter_kmean=200,
  c1=2,
  c2=2
  `
  - Ejecutar ACDE en el conjunto iris.
    - Después de correr todo el código de la libreta obtenemos los parámetros $x_{min}$ , $x_{max}$ y $datos$ ejecutando en una celda nueva el siguiente código:
        ```
      with open(ruta/ParametrosIris.pickle, "rb") as f:
          iris_datos,iris_min,iris_max = pickle.load(f)
      ```
      **nota: debemos cambiar "ruta" por la dirección donde descargamos el archivo ParametrosIris.pickle**
    - Llamamos a la función principal con los parámetros que obtuvimos, para este ejemplo usaremos los mismos valores que en el trabajo de tesis, para este ejemplo $k$ = 3 y la función aptitud será “aptitud”.
        ```
        pso(x_min = iris_min,x_max = iris_max,v_min = 0,v_max = 1,k = 3,
        n_part = 10,iter_pso = 800,iter_kmean = 200, c1 = 2,c2 = 2,datos = iris_datos,f_apt = aptitud)
      
        ```
        **nota: lo anterior nos devuele un objeto, vea sus propiedades al inicio de este ejemplo**
      
  #### [SAGMDE](/SAGMDErecocido.ipynb)


  ```
  with open(archivo, "rb") as f:
      datos,x_min,x_max = pickle.load(f)
  ```



## Replicar resultados obtenidos en la tesis.



















