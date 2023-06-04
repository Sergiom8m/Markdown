# Diagramas en *Markdown*

*Markdown* permite crear diferentes tipos de diagramas a sus usuarios.

## Diagramas de flujo

Para crear diagramas de flujo en *Markdown* se puede utilizar *mermaid* e insertaremos el diagrama como si fuese un codigo de lenguaje *mermaid*.

Primeramente añadiremos el tipo de diagrama seguido de las letras `TB` que sirven para que el diagrama aparezca verticalmente. Si se desea que el diagrama aparezca en horizontal se utilizara `LR`

```markdown
```mermaid
flowchart TB
\```        (no usar \, es para escapar los caracteres)
```

Cada nodo se pondra en una linea, primero se pondra el identificador del nodo y despues el contenido textual del mismo envuelto en [ ]. Los caracteres especiales que envuelven el contenido del nodo dictaminan cual sera la forma de ese nodo. Existen las siguientes opciones:

<br>

Nodo de inicio/fin:

```markdown
A(Inicio)
```

```mermaid
flowchart TB
A(Inicio)
```      

Nodo de proceso:

```markdown
A[Proceso]
```

```mermaid
flowchart TB
A[Proceso]
```  

Nodo de decision:

```markdown
A{Decision}
```

```mermaid
flowchart TB
A{Decision}
```  

Nodo de entrada/salida:

```markdown
A[/Input/]
```

```mermaid
flowchart TB
A[/Input/]
```  

```markdown
A[\Output\]
```

```mermaid
flowchart TB
A[\Output\]
```  

Nodo de subrutina:

```markdown
A[[Subrutina]]
```

```mermaid
flowchart TB
A[[Subrutina]]
```  

Nodo de base de datos:

```markdown
A[(DB)]
```

```mermaid
flowchart TB
A[(DB)]
```  

Una vez conocida la sintaxis de cada uno de los tipos de nodo, es importante saber como se unen entre si. Siguiendo la estructura de *mermaid* añadiremos la primera linea con el tipo de diagrama y `TB` seguido de todos los nodos. Despues se añadira lo siguiente para unir los nodos:

```markdown
```mermaid
flowchart TB
    A(Inicio)
    B[/Escribe tu contraseña/]
    C[\psw\]
    D{psw = '1234'}
    E[/Login correcto/]
    F[/Login incorrecto, try again/]
    G(Fin)

    A-->B-->C-->D

    D--> |True| E
    D--> |False| F

    E-->G
    F-->B
\```
```

```mermaid
flowchart TB
    A(Inicio)
    B[/Escribe tu contraseña/]
    C[\psw\]
    D{psw = '1234'}
    E[/Login correcto/]
    F[/Login incorrecto, try again/]
    G(Fin)

    A-->B-->C-->D

    D--> |True| E
    D--> |False| F

    E-->G
    F-->B
```

<br>

Si se desea añadir un titulo al diagrama se añadira lo siguiente en el codigo anterior:

```markdown
```mermaid
---
title: Login flowchart
---
flowchart TB
    A(Inicio)
    B[/Escribe tu contraseña/]
    C[\psw\]
    D{psw = '1234'}
    E[/Login correcto/]
    F[/Login incorrecto, try again/]
    G(Fin)

    A-->B-->C-->D

    D--> |True| E
    D--> |False| F

    E-->G
    F-->B
\```
```

```mermaid
---
title: Login flowchart
---
flowchart TB
    A(Inicio)
    B[/Escribe tu contraseña/]
    C[\psw\]
    D{psw = '1234'}
    E[/Login correcto/]
    F[/Login incorrecto, try again/]
    G(Fin)

    A-->B-->C-->D

    D--> |True| E
    D--> |False| F

    E-->G
    F-->B
```

<br>

Si se quieren añadir lineas discontinuas se empleara la siguiente sintaxis:


```markdown
A-.->B
```

```mermaid
flowchart TB
    A(Inicio)
    B[/Escribe tu contraseña/]

    A-.->B
```


<br>

Por otra parte, si se desea añadir texto *Markdown* dentro se debe de encerrar entre "``"

```markdown
A("`Esto es **Texto** Markdown`")
```

```mermaid
flowchart TB
    A("`Esto es **Texto** Markdown`")
```

<br>

Por ultimo, se pueden crear subgrafos dentro de un mismo diagrama de flujo. Para ello se emplea la siguiente estructura:

```markdown
```mermaid
flowchart TB
    
    A-->B
    subgraph Fase1
    B-->C
    C-->D
    D-->E
    end
    subgraph Fase2
    E-->F
    F-->G
    end
    subgraph Fase3
    G-->H
    H--I
    end
\```
```
El resultado seria el siguiente:

```mermaid
flowchart LR
    
    A-->B

    subgraph Fase1
    B-->C
    C-->D
    D-->E
    end

    subgraph Fase2
    E-->F
    F-->G
    end

    subgraph Fase3
    G-->H
    H-->I
    end

```

**PARA MAS INFORMACION:**

[Mermaid](https://mermaid.js.org/syntax/flowchart.html)














