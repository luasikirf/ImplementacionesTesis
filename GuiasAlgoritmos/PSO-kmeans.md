# Explicación de los parámetros que recibe el algoritmo.
Para el correcto funcionamiento de este algoritmo requerimos de 12 parámetros, los cuales son:  

 `
  x_min, x_max, v_min ,v_max ,k , n_part, iter_pso, iter_kmean, c1, c2, datos, f_apt
  `

  Vamos a dividirlos en 2 grupos, los que nosotros podemos ajustar y los que no.
- Ajustables.  
  Estos parámetros los puedes cambiar y ponerle los valores que necesites.
  - v_min: es la velocidad mínima a la que se mueve una partícula.
  - v_max: es la velocidad máxima a la que se mueve una partícula.
  - n_part: es la cantidad de partículas que conforman el cumulo, a mayor valor hace que el algoritmo se alenté, pero aumenta su capacidad de búsqueda.
  - iter_pso: número de iteraciones para la parte de PSO, recomendaría usar valores altos sin miedo, pues si no se encuentra una mejor solución a la actual en 10 iteraciones sale del ciclo, mientras que con valores bajos podría no encontrar el óptimo.
  - iter_kmean: número de iteraciones para la parte de kmeans, misma recomendacion que con iter_pso.
  - f_apt: función la cual buscará maximizar el algoritmo, puedes por defecto usar **aptitud** o **aptitid2**, la primera es la que usa originalmente el algoritmo, la segunda se basa en el índice DB, también puedes usar cualquier otra mandándola como alrgumento.
  - datos: deben estar en forma de array, puedes meter los datos que quieras mientras cumplan el formato.
  
-  No ajustables.

  
      Los siguientes parámetros deben tener un formato especifico de acuerdo al conjunto de datos que le ingresas.  
     
     - x_min: Debe ser un arreglo de tamaño $D$, siendo $D$ la dimensión de los datos, los valores que contiene son los mínimos que puede adquirir cada componente de los datos.
     - x_max: Debe ser un arreglo de tamaño $D$, siendo $D$ la dimensión de los datos, los valores que contiene son los máximos que puede adquirir cada componente de los datos.
     - k: es la cantidad de grupos que va a formar el algoritmo, debe ser la misma cantidad de grupos que tienen los datos, pero si no la conoces puedes indicarle en cuantos grupos quieres que divida los datos.
  
    Los siguientes parámetros los puedes cambiar, pero el valor recomendado lo dan los autores de PSO tras experimentar con muchos otros.
    - c1: se recomienda el valor de 2.
    - c2: se recomienda el valor de 2.
