# Taller de Algoritmos geneticos

### Presentado por:
- **Ángel Rivera Amortegui**
- **Daniel Echeverri Jimenez**

---

## **Punto 1: Distribucion de poder politico**
Archivo: [AlgGen_poderPolitico.ipynb](./AlgGen_poderPolitico.ipynb)  
Descripción: Los curules se distribuyeron de la siguiente manera: Para los primeros 4 partidos se utilizo una variable de distribución exponencial de media 50/5=10. Se utilizo la siguiente formula:

V = -10Ln(U(0,1))

Donde U(0,1) es una variable de distribución uniforme entre 0 y 1. Para el quinto partido se sumo el total de curules entre los otros cuatro partidos y se le resto el resultado a 50.

partido |   #   |   curules
--------|-------|------------
partido |   1   |   8
partido |   2   |   8
partido |   3   |   16
partido |   4   |   13
partido |   5   |   5

Las 50 entidades tienen un peso político distribuido de la siguiente manera:

Entidades   |   Poder político
------------|-------------------
Biblioteca central  |	71
Teatro mayor    |	20
Hospital central    |	63
Estadio |	5
Hospital principal  |	83
Plaza central   |	46
Iglesia grande  |	49
Biblioteca del norte    |	37
Iglesia pequeña |	2
Centro comercial    |	26
Centro financiero   |	49
Palacio del gobierno    |	99
Colegio distrital   |	85
Universidad distrital   |	46
Iglesia principal   |	83
Banco central   |	37
Superintendencia    |	15
Ministerio de defensa   |	40
Corte suprema   |	40
Instituto investigativo |   13
Aeropuerto  |	84
Banco nacional  |	48
Centro de estudios  |	97
Centro de investigación |	64
Dirección general   |	15
Cámara  |	38
Agencia tributaria  |	50
Fondo monetario |	49
Instituto central   |	19
Administración federal  |	59
Ministerio de defensa   |	39
Comisión nacional   |	73
Instituto de ciencias   |	52
Policía nacional    |	4
Comisión reguladora |	57
Ministerio de vivienda  |	24
Corte constitucional    |	75
Secretaria de cultura   |	98
Banco de desarrollo |   5
Agencia ambiental   |	25
Ministerio publico  |	39
Secretaria de economía  |	48
Ministerio de turismo   |	91
Gran teatro	|   32
Dirección de infraestructura    |	77
Consejo de administración	|   81
Instituto estadístico	|   4
Agencia de transporte	|   21
Agencia de migración	|   11
Agencia de regulación	|   63

Para solucionar el problema, la estructura de los candidatos es de la siguiente manera:

Un candidato se representa con una lista de 50 cromosomas, donde el i-esimo elemento de la lista indica a que partido pertenece la i-esima entidad según el orden de la lista anterior.

Un cromosoma es un numero binario de 3 bits que indica el partido al que pertenece la entidad. El numero i representa al partido i-1. Si el partido i-1 no existe el candidato recibe una penalización en su evaluación de aptitud.

Se evalúa al candidato según el poder político que consiga el partido 1, con penalizaciones por asignar entidades a partidos que no existen y por asignar a un partido mas entidades de las que pueden tener. Si esto ocurre con el partido 1, no se darán puntos por el peso político de los curules de más.


---

## **Punto 2: Logisticas de la empresa de energia**
Archivo: [Energía_eléctrica.ipynb](./Energía_eléctrica.ipynb)  
Descripción: El codigo encuentra la mejor distribucion de despacho de energia por parte de una empresa de energia electrica, con tal que cumpla con los objetivos y genere la menor cantidad de costos.

---

## **Punto 3: Laboratorio de TSP**
Archivo: [  ](./    )  
Descripción: 

---

## **Punto 4: 50 palabras**
Archivo:  [50_palabras.ipynb](./50_palabras.ipynb)  
Descripción: El programa llega a una palabra del usuario a partir de una poblacion de 50.

---

## **Punto 5: PyGad**
Archivo:  [AlgGen_PyGad.ipynb](./AlgGen_PyGad.ipynb)  
Descripción: El programa utiliza la libreria PyGad para resolver el problema del punto 1.
