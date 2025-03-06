# Taller de Algoritmos Genéticos

### Presentado por:
- **Ángel Rivera Amortegui**
- **Daniel Echeverri Jimenez**

---

## **Punto 1: Matriz de poder para repartir el poder usando AGs.**
Archivo: [AlgGen_poderPolitico.ipynb](./AlgGen_poderPolitico.ipynb)

Descripción: Este código implementa un algoritmo genético para resolver un problema de asignación de curules a partidos políticos basado en el peso político de diferentes entidades. El objetivo es asignar entidades a los partidos de manera que se respeten las restricciones de curules disponibles para cada partido, maximizando el puntaje obtenido de acuerdo al peso político de las entidades. A continuación se realizar una breve explicación del código.
- Generación de cromosomas: Se crean soluciones aleatorias donde cada bit indica la asignación de una entidad a un partido.
- Evaluación: Se calcula un puntaje de aptitud según si las asignaciones respetan las restricciones de curules y el peso político de las entidades.
- Selección de padres: Los cromosomas con mejores puntajes tienen más probabilidad de ser seleccionados para la siguiente generación.
- Cruce y mutación: Se combinan los cromosomas de los padres para generar nuevos, con algunas mutaciones aleatorias para evitar soluciones subóptimas.
- Iteración: El proceso se repite durante un número de iteraciones, imprimiendo los resultados al final. Con este enfoque busca encontrar la mejor asignación de entidades a partidos de manera eficiente, respetando las restricciones impuestas.
- Descripción: Los curules se distribuyeron de la siguiente manera: Para los primeros 4 partidos se utilizo una variable de distribución exponencial de media 50/5=10. Se utilizo la siguiente formula:

V = -10Ln(U(0,1))

Donde U(0,1) es una variable de distribución uniforme entre 0 y 1. Para el quinto partido se sumo el total de curules entre los otros cuatro partidos y se le resto el resultado a 50.
## Distribución de Curules por Partido

| Partido   | # | Curules |
|-----------|---|---------|
| Partido 1 | 1 | 8       |
| Partido 2 | 2 | 8       |
| Partido 3 | 3 | 16      |
| Partido 4 | 4 | 13      |
| Partido 5 | 5 | 5       |

## Distribución del Poder Político en las Entidades

| Entidad                      | Poder Político |
|------------------------------|----------------|
| Biblioteca central           | 71             |
| Teatro mayor                 | 20             |
| Hospital central             | 63             |
| Estadio                      | 5              |
| Hospital principal           | 83             |
| Plaza central                | 46             |
| Iglesia grande               | 49             |
| Biblioteca del norte         | 37             |
| Iglesia pequeña              | 2              |
| Centro comercial             | 26             |
| Centro financiero            | 49             |
| Palacio del gobierno         | 99             |
| Colegio distrital            | 85             |
| Universidad distrital        | 46             |
| Iglesia principal            | 83             |
| Banco central                | 37             |
| Superintendencia             | 15             |
| Ministerio de defensa        | 40             |
| Corte suprema                | 40             |
| Instituto investigativo      | 13             |
| Aeropuerto                   | 84             |
| Banco nacional               | 48             |
| Centro de estudios           | 97             |
| Centro de investigación      | 64             |
| Dirección general            | 15             |
| Cámara                       | 38             |
| Agencia tributaria           | 50             |
| Fondo monetario              | 49             |
| Instituto central            | 19             |
| Administración federal       | 59             |
| Ministerio de defensa        | 39             |
| Comisión nacional            | 73             |
| Instituto de ciencias        | 52             |
| Policía nacional             | 4              |
| Comisión reguladora          | 57             |
| Ministerio de vivienda       | 24             |
| Corte constitucional         | 75             |
| Secretaria de cultura        | 98             |
| Banco de desarrollo          | 5              |
| Agencia ambiental            | 25             |
| Ministerio público           | 39             |
| Secretaria de economía       | 48             |
| Ministerio de turismo        | 91             |
| Gran teatro                  | 32             |
| Dirección de infraestructura | 77             |
| Consejo de administración    | 81             |
| Instituto estadístico        | 4              |
| Agencia de transporte        | 21             |
| Agencia de migración         | 11             |
| Agencia de regulación        | 63             |

Para solucionar el problema, la estructura de los candidatos es de la siguiente manera:

Un candidato se representa con una lista de 50 cromosomas, donde el i-esimo elemento de la lista indica a que partido pertenece la i-esima entidad según el orden de la lista anterior.

Un cromosoma es un numero binario de 3 bits que indica el partido al que pertenece la entidad. El numero i representa al partido i-1. Si el partido i-1 no existe el candidato recibe una penalización en su evaluación de aptitud.

Se evalúa al candidato según el poder político que consiga el partido 1, con penalizaciones por asignar entidades a partidos que no existen y por asignar a un partido mas entidades de las que pueden tener. Si esto ocurre con el partido 1, no se darán puntos por el peso político de los curules de más.

## **Punto 2: Usar un AGs en un despacho de energía para minimizar los costos de transporte y generación de energía**

Archivo: [3_2_Energía_eléctrica.ipynb](./3_2_Energía_eléctrica.ipynb)  
Descripción:Este código resuelve un problema de optimización lineal utilizando la librería pulp, donde se busca minimizar los costos de transporte y generación de energía entre varias plantas y ciudades. Define las cantidades disponibles de energía en cada planta, la demanda de energía en cada ciudad, y los costos asociados tanto al transporte como a la generación. Las variables de decisión representan la cantidad de energía transportada entre cada planta y ciudad. Luego, establece restricciones de oferta y demanda, y resuelve el problema. Finalmente, muestra una tabla con los resultados, detallando los costos de transporte, generación y el costo total del suministro.

## **Punto 3: Solución de un TSP (Traveling Salesman Problem), el problema de un viajero en Colombia:**

Archivo: [El_problema_del_viajero_en_ciudades_de_Colombia.ipynb](./El_problema_del_viajero_en_ciudades_de_Colombia.ipynb)  
Descripción: Este código implementa un algoritmo genético para resolver el problema del Viajante de Comercio (TSP) utilizando un conjunto de ciudades colombianas y sus coordenadas geográficas. El algoritmo comienza creando una población inicial de rutas aleatorias entre las ciudades. A continuación, evalúa el "fitness" de cada ruta, que se define como la distancia total recorrida, e implementa la selección por torneo para elegir a los mejores individuos. Posteriormente, se aplica el cruce para generar nuevas rutas (descendencia) y una mutación para introducir variabilidad. El proceso se repite durante un número determinado de generaciones para optimizar la ruta y encontrar la mejor solución posible en términos de distancia total recorrida. Finalmente, el código devuelve la mejor ruta encontrada y su distancia total.

La simulacion, evaluada en 50 generaciones, dio un resultado con una distancia, en valor de coordenadas, de 38.97.

## **Punto 4: Generación aleatoria para una población de 50 palabras **

Archivo: [3_4_50_palabras.ipynb](./3_4_50_palabras.ipynb)  
Descripción: Este código implementa un algoritmo genético para encontrar una palabra objetivo (en este caso, "GENETICA") mediante un proceso de evolución simulada. Inicia generando una población aleatoria de palabras y luego evalúa qué tan cerca están de la palabra objetivo usando una función de aptitud. La aptitud se mide por la cantidad de caracteres coincidentes entre una palabra de la población y la palabra objetivo. Posteriormente, los individuos más aptos se seleccionan para cruzarse y producir descendencia, aplicando mutaciones aleatorias a cada generación. El proceso continúa hasta encontrar la palabra objetivo o alcanzar el número máximo de generaciones.

En la prueba del programa se encontro la palabra objetivo en 29 generaciones.

## **Punto : Se utiliza la libreria PyGad para resolver el problema del punto 1.**

Archivo: [AlgGen_PyGad.ipynb](./AlgGen_PyGad.ipynb) 

## **Punto 6: Un AGs para una máquina despulpadora de café (Punto de investigación adicional)**

Archivo: -[AGS_máquina_despulpadora_de_café.ipynb](./AGS_máquina_despulpadora_de_café.ipynb)
Descripción: Este código implementa un algoritmo genético (AG) para optimizar la velocidad de una máquina en función de dos factores: la eficiencia y los defectos. La eficiencia sigue una curva tipo campana centrada en 200 RPM, mientras que los defectos aumentan linealmente con la velocidad. El AG evoluciona una población de posibles soluciones (velocidades) a lo largo de varias generaciones, seleccionando los mejores individuos, cruzándolos para generar nuevos, y aplicando mutaciones aleatorias para explorar soluciones adicionales. Al final, el algoritmo muestra la velocidad óptima encontrada para maximizar la eficiencia mientras minimiza los defectos, dentro de un rango de 50 a 300 RPM.

### Notas adicionales:
Este repositorio contiene la resolución detallada de los puntos del taller 3 sobre algoritmos genéticos. Cada programa ha sido documentado con descripciones claras para facilitar su comprensión y replicación.