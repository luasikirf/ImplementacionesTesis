# Explicación de los parámetros que recibe el algoritmo.
Para el correcto funcionamiento de este algoritmo requerimos de 10 parámetros, los cuales son:
`
datos, n_g, T, T_f, T_dist, T_dist_f, alpha, alpha_dist, MaxIter, f_obj
`
Vamos a dividirlos en 2 grupos, los que nosotros podemos ajustar y los que es recomendable no hacerlo.
- Ajustables.  
  Estos parámetros los puedes cambiar y ponerle los valores que necesites.
  - n_g: es la cantidad de grupos que va a formar el algoritmo, debe ser la misma cantidad de grupos que tienen los datos, pero si no la conoces puedes indicarle en cuantos grupos quieres que divida los datos.
  - datos: deben estar en forma de array, puedes meter los datos que quieras mientras cumplan el formato.
  - MaxIter: número máximo de iteraciones en cada temperatura, un valor alto aumenta la búsqueda de soluciones pero aumenta el tiempo de ejecución.
  - f_obj: función que se busca minimizar, para usar la que viene por defecto usa **costo**, si quieres usar otra pásala como argumento. 
-  No se recomienda cambiarlos.  
  Estos parámetros tienen un valor proporcionado por los autores, si se quiere repplicar lo obtenido en el trabajo de tesis no debes moverlos, pero si buscas experimentar puedes cambiarlos libremente.
   - T: temperatura inicial del sistema, se usa para la mutación  gaussiana.
   - T_f: temperatura final del sistema, se usa para la mutación  gaussiana.
   - T_dist: temperatura inicial del sistema, se usa para la mutación distorsión y utilidad.
   - T_dist_f: temperatura final del sistema, se usa para la mutación distorsión y utilidad.
   - alpha: factor de escalado de T, determina que tan rápido disminuye.
   - alpha_dist: factor de escalado de T_dist, determina que tan rápido disminuye.
