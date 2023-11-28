# Explicación de los parámetros que recibe el algoritmo.
Para el correcto funcionamiento de este algoritmo requerimos de 9 parámetros, los cuales son:

` cr_max ,cr_min ,tPoblacion ,
  k_max ,x_min ,x_max ,nLlamadas ,
  datos, index='cs'
`
Vamos a dividirlos en 2 grupos, los que nosotros podemos ajustar y los que no.
- Ajustables.  
  Estos parámetros los puedes cambiar y ponerle los valores que necesites.
  - cr_max: junto a cr_min controlan la probabilidad de que un individuo herede las propiedades de un solo padre o de ambos, a mayor valor de estas variables heredará las caracteristicas del segundo padre.
  - cr_min: junto a cr_max controlan la probabilidad de que un individuo herede las propiedades de un solo padre o de ambos, a mayor valor de estas variables heredará las caracteristicas del segundo padre.
  - tPoblacion: indica la cantiad de individuos que conforman la población. Aumentando los individuos en la población se exploran más soluciones factibles a la vez, pero aumenta el tiempo de ejecución. 
  - k_max: es la cantidad máxima de grupos a formar. Elevar este numero puede provocar que el algoritmo “pierda tiempo” buscando dividir los datos en más cantidades de grupos, si los datos tienen 3 grupos y pones k_max = 30, seria una perdida de tiempo que busque soluciones con 4 grupos o más.
  - nLlamadas: es la cantidad máxima de llamadas a la función objetivo que puede realizar el programa, un valor pequeño puede hacer que no se encuentre la solución óptima, mientras que un valor alto incrementa el tiempo de ejecución. 
  - index: indica cual índice de validación queremos usar, por defecto el codigo cuenta con los 2 usados en el trabjo de tesis, “CS” y “DB”, “CS” viene por defecto, para usar “DB” basta con ponerlo entre comillas ‘DB’. 
-  No ajustables.  
  Estos parámetros deben tener un formato especifico de acuerdo al conjunto de datos que le ingresas.
   - x_min: Debe ser un arreglo de tamaño $D$, siendo $D$ la dimensión de los datos, los valores que contiene son los mínimos que puede adquirir cada componente de los datos.
   - x_max: Debe ser un arreglo de tamaño $D$, siendo $D$ la dimensión de los datos, los valores que contiene son los máximos que puede adquirir cada componente de los datos.
