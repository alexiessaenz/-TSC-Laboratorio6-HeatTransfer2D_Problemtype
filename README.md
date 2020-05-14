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

CONDTYPE: Type of entity which the condition is to be applied to. 
This includes the parameters "over points", "over lines", "over surfaces", “over volumes” or "over layers". 

CONDMESHTYPE: Type of entity of the mesh where the condition is to be applied. 
The possible parameters are "over nodes", "over body elements" or “over face elements”. 

### Materials File (.mat)

Permite definir los materiales y las propiedades de estos

```
NUMBER: 1 MATERIAL: Material1
QUESTION: k
VALUE: 0.5
END MATERIAL
```

### Template File (.bas)

Describes the format and structure of the required data input file for the solver that is used for a
particular case. 

#### Comandos utilizados en este archivo

All these commands must be prefixed by a character *

*GenData. This must carry an argument of integer type that specifies the number of the field to be printed. This
number is the order of the field inside the general data list. This must be one of the values that are fixed for the whole
problem, independently of the interval 

*npoin, *ndime, *nnode, *nelem, *nmats, *nintervals. These return, respectively, the number of points, the
dimensions of the project being considered, the number of nodes of the element with the highest number, the number
of elements, the number of materials and the number of data intervals. All of them are considered as integers 

*CondNumEntities. You must have previously selected a condition (see *set cond). This returns the number of
entities that have a condition assigned over them.
*ElemsNum: This returns the element's number.
*NodesNum: This returns the node's number.

*NodesCoord. This command writes the node's coordinates. It must be inside a loop (see *loop) over the nodes or
elements. 

If *NodesCoord receives an integer argument (from 1 to 3) inside a loop of nodes, this argument indicates which
coordinate must be written: x, y or z. Inside a loop of nodes:
*NodesCoord writes three or two coordinates depending on how many dimensions there are.
*NodesCoord(1) writes the x coordinate of the actual node of the loop.
*NodesCoord(2) writes the y coordinate of the actual node of the loop.

*ElemsConec. This command writes the element's connectivities, i.e. the list of the nodes that belong to the element,
displaying the direction for each case.

The *OnlyInCond modifier implies that the iteration will only take place over the entities that satisfy the relevant
condition. This condition must have been previously defined with *set cond. 

<hr>
<p align="center">Para servirles, <strong>Equipo de Instructores</strong> </p>
