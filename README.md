# Laboratorio 6 - Problem Type
Técnicas de Simulación en Computadoras: Sexta práctica de laboratorio 

## Contenido

<p align="center">Archivos del Problem Type para Transferencia de Calor en dos dimensiones</p>

### Problem and Intervals File (.prb)

```
PROBLEM DATA
QUESTION: k
VALUE: 0
QUESTION: Q
VALUE: 0
END PROBLEM DATA
```

El orden de las variables en este archivo es importante.

### Conditions File (.cnd)

Permite establecer el tipo de condiciones

```
NUMBER: 1 CONDITION: Dirichlet
CONDTYPE: over lines
CONDMESHTYPE: over nodes
QUESTION: T
VALUE: 0
END CONDITION
NUMBER: 2 CONDITION: Neumann
CONDTYPE: over lines
CONDMESHTYPE: over nodes
QUESTION: dTdn
VALUE: 0
END CONDITION
```

CONDTYPE: Entidad donde se aplicaran las condiciones.
Acepta como parametros: "over points", "over lines", "over surfaces", “over volumes”, "over layers". 

CONDMESHTYPE: Entidad de la malla donde se aplicaran las condiciones.
Acepta como parametros: "over nodes", "over body elements", “over face elements”. 

### Materials File (.mat)

Permite definir los materiales y las propiedades de estos

```
NUMBER: 1 MATERIAL: Material1
QUESTION: k
VALUE: 0.5
END MATERIAL
```

### Template File (.bas)

Describe la estructura de la data que se utilizara como entrada para el problema a resolver.

#### Comandos utilizados en este archivo

Los comandos deben ser precedidos por el caracter *

*GenData 
Recibe como argumento un entero que especifica el campo del data list e imprime ese dato.  

*npoin, *nelem 
Devuelven el número de nodos y el número de elementos respectivamente.

*CondNumEntities
Devuelve el número de entidades que tienen asignada una condición.
Esta condición se selecciona previamente con *set cond

*ElemsNum: Devuelve el número del Elemento.

*NodesNum: Devuelve el número del Nodo.

*NodesCoord. 
Devuelve las coordenadas de un nodo, debe estar dentro de un *loop

Recibe como argumento un número entre 1 a 3.

*NodesCoord(1) devuelve la coordenada en X.

*NodesCoord(2) devuelve la coordenada en Y.

*ElemsConec. 
Devuelve la lista de nodos que pertenecen a un elemento.

*OnlyInCond
La iteración solo incluirá entidades que tienen asignada una condición.
Esta condición se selecciona previamente con *set cond

<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>
