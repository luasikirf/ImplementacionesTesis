Todos los archivos **.pickle** contienen 3 variables: **datos**, **x_min** y **x_max**, todas en formato array de numpy, la variable datos contiene el conjunto de datos, **x_min** es un array con los valores mínimos de cada componente de los datos, **x_max** es por su parte el array con los máximos valores que adquieren los datos.  
Para recuperar los valores de las variables basta con ejecutar el siguiente código:
  ```
  with open(archivo, "rb") as f:
      datos,x_min,x_max = pickle.load(f)
  ```
En el cual debemos cambiar la variable **archivo** por la dirección del archivo que queremos extraer, podemos renombrar **datos**,**x_min** y **x_max** como queramos para identificarlos mejor.
