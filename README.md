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
  Tenemos que ejecutar la siguiente función.
  ```
  acde(cr_max: float,cr_min: float,tPoblacion: int,
         k_max: int,x_min: float,x_max: float,nLlamadas: int,
         datos, index='cs')
  ```
 La descripción de la función de cada parámetro se encuentra en el código.  $jjj$
 Los parámetros utilizados en el trabajo de tesis son los siguientes:
   ```
  acde(cr_max = 1,cr_min 0 0.5,tPoblacion = 10,
         k_max = 20,x_min: float,x_max: float,nLlamadas = 100000,
         datos, index='cs')
  ```

- [PSO-Kmeans](/PSO-kmeans.ipynb)
  
- [SAGMDE](SAGMDErecocido.ipynb)
