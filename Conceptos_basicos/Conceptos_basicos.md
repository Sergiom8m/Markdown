# Conceptos basicos *MARKDOWN*

<br>

## Comentarios

Antes de comenzar con la sintaxis de *Markdown* es importante saber que para introducir comentarios en el codigo se utiliza la siguiente estructura:

```html
<!-- Texto comentado -->
```

<br>

## Tipografia 

Para escribir parrafos en *Markdown* no hay que utilizar ninguna etiqueta, simplemente escribiremos el texto en el editor directamente.

```html
El parafo va escrito de esta forma, sin etiquetas.
```

Si se quiere aplicar italica se utilizara * antes y despues del texto que se quiere poner en italica.

Atajo teclado: Ctrl + I

```markdown
*El texto en italica va envuelto en un solo asterisco*
```

Si se quiere aplicar negrita se utilizara ** antes y despues del texto que se quiere poner en negrita.

Atajo teclado: Ctrl + B

```markdown
**El texto en negrita va envuelto en dos asteriscos**
```

Por supuesto, estos dos tipos de modificaciones textuales son compatibles entre si y se pueden aplicar ambas sobre un mismo texto.

```markdown
_**Las dos tiopografias se pueden combinar**_
```

Ademas de los elementos base de *Markdown* se pueden usar elementos *HTML* para suplir las carencias del lenguaje de *Markdown*

Por ejemplo, si se quiere alinear un texto y darle color se puede hacer mediante *HTML* con las etiquetas `<center>` y `<p>`.

```html
<center> <p style="color:red">Texto centrado y en rojo</p></center>
```

El resultado seria el siguiente:

<center> <p style="color:red">Esta etiqueta sirve para centrar el texto</p></center>


<br>

## Encabezados

Para los encabezados se emplean hashes seguidos de espacio al principio del texto. El numero de hashes define el nivel del encabezado.

```markdown
# Con un solo hash el encabezado seria de nivel 1
## Con dos hashes el encabezado seria de nivel 2
### Con tres hashes el encabezado seria de nivel 3
...
...
...
```

<br>

## Enlaces externos

Los enlaces externos se utilizan para redireccionar al usuario a alguna direccion ajena al documento.

Si se quiere que el enlace quede visible unicamente se ha de envolver la URI en <>.

```markdown
<https://youtube.es> 
```

Visualmente se veria de  esta forma:

<https://youtube.es> 

Si por el contrario se desea modificar el texto que aparecera utilizaremos la siguiente sintaxis:

```markdown
[YOUTUBE](https://youtube.es) 
```
Visualmente se veria de  esta forma:

[YOUTUBE](https://youtube.es) 

Por ultimo, si se quiere referenciar un recurso local (Ubicado en un path local) se empleara la siguiente sintaxis:

```markdown
[RECURSO LOCAL](/path/hacia/el/recurso/local)
```

Visualmente se veria de esta forma:

[RECURSO LOCAL](/Referenciable.txt)


<br>

## Enlaces internos

*Markdown* permite enlazar de manera interna unicamente los encabezados. Estos de por si ya cuentan con un enlace inteno preestablecido. Para hacer uso de ellos se debe utilizar la siguiente sintaxis:

```markdown
[ENLACE AL PRINCIPIO](#conceptos-basicos-markdown)
```

**Nota**: Los espacios en los titulos de los encabezados se codifican con guiones

Visualmente se veria de esta forma:

[ENLACE AL PRINCIPIO](#conceptos-basicos-markdown)


<br>

## Listas

En *Markdown* existen dos tipos de listas; las listas ordenadas y las listas desordenadas.

Las listas ordenadas se crean de la siguiente manera:

```markdown
1. PRIMER ELEMENTO
   1. SUB-ELEMENTO 1
   2. SUB-ELEMENTO 2
   3. SUB-ELEMENTO 3
2. SEGUNDO ELEMENTO
3. TERCER ELEMENTO
```

Y para crear lista desordenadas, se hara de esta forma:

```markdown
- PRIMER ELEMENTO
  - SUB-ELEMENTO 1
  - SUB-ELEMENTO 2
  - SUB-ELEMENTO 3
- SEGUNDO ELEMENTO
- TERCER ELEMENTO
```


<br>

## Tablas

Para crear una tabla simple en *Markdown* la sintaxis es muy sencilla, simplemente se ha de crear una tabla con caracteres especiales.

```markdown
| NOMBRE | EDAD | CORREO |
|--------|------|--------|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |
```

El resultado sera el siguiente:

| NOMBRE | EDAD | CORREO |
|--------|------|--------|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |


Por defecto *Markdown* alinea los elementos de las tablas al lado izquierdo. Sin embargo eso se puede cambiar añadiendo : en la segunda fila que sirve de divisor entre las cabeceras y los datos. Se hace de la siguiente forma:

```markdown
| ALINEADO IZQ | CENTRADO | ALINEADO DERECHA |
|:------------------|:--------:|-----------------:|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |
```

El resultado sera el siguiente:

| ALINEADO IZQ | CENTRADO | ALINEADO DERECHA |
|:------------------|:--------:|-----------------:|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |

Por otro lado, existe la posibilidad de crear tablas sin cabeceras. Para ello en los espacios correspondientes a las cabeceras se introducira un comentario vacio.

```markdown
| <!-- -->  | <!-- -->  | <!-- -->  |
|-----------|-----------|-----------|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |
```

El resultado sera el siguiente:

| <!-- -->  | <!-- -->  | <!-- -->  |
|-----------|-----------|-----------|
| SERGIO | 20 | sergio@gmail.com |
| ANDONI | 32 | andoni@gmail.com |
| RAUL | 45 | raul@gmail.com |

Por ultimo, si se quieren fusionar celdas se ha de emplear lenguaje *HTML* puesto que *Markdown* no da esa opcion.

```html
<table>
    <thead>
        <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>Column 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4 align="center">R1 Text</td>
            <td rowspan=2 align="center">R2 Text A</td>
            <td align="center">R3 Text A</td>
        </tr>
        <tr>
            <td align="center">R3 Text B</td>
        </tr>
        <tr>
            <td rowspan=2 align="center">R2 Text B</td>
            <td align="center">R3 Text C</td>
        </tr>
        <tr>
            <td align="center">R3 Text D</td>
        </tr>
    </tbody>
</table>
```

Visualmente qudaria algo asi:

<table>
    <thead>
        <tr>
            <th>Column 1</th>
            <th>Column 2</th>
            <th>Column 3</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td rowspan=4 align="center">R1 Text</td>
            <td rowspan=2 align="center">R2 Text A</td>
            <td align="center">R3 Text A</td>
        </tr>
        <tr>
            <td align="center">R3 Text B</td>
        </tr>
        <tr>
            <td rowspan=2 align="center">R2 Text B</td>
            <td align="center">R3 Text C</td>
        </tr>
        <tr>
            <td align="center">R3 Text D</td>
        </tr>
    </tbody>
</table>

<br>

## Imagenes

Para introducir imagenes en *Markdown* se empleara codigo *HTML*. Es cierto que *Markdown* ofrece la posibilidad de incluir imagenes pero se crean menos incidencias usando codigo *HTML*.

```html
<!-- Imagen de internet -->
<img src=https://geekytheory.com/content/images/2014/03/markdown_inte-1024x630.png>

<!-- Imagen local -->
<img src=/Referenciable.jpg>
```

El resultado seria el siguiente:

<!-- Imagen de internet -->
<img src=https://geekytheory.com/content/images/2014/03/markdown_inte-1024x630.png>

<!-- Imagen local -->
<img src=Referenciable.jpg>

<br>

## Citas

En lenguaje *Markdown* para insertar citas se añade un > al comienzo del texto.

```markdown
> "Solo se que no se nada." - Socrates
```

El resultado seria este:

> "Solo se que no se nada." - Socrates

Se pueden tambien incluir citas en varias lineas de esta forma:

```markdown
> "Todo lo que escuchamos es una opinion, no un hecho. 
>
> Todo lo que vemos es una perspectiva, no la verdad."
>
> Marco Aurelio
```

El resultado seria este:

> "Todo lo que escuchamos es una opinion, no un hecho. 
>
> Todo lo que vemos es una perspectiva, no la verdad."
>
> Marco Aurelio

<br>

## Codigo

*Markdown* incluye 2 funciones que son muy utiles cuando se utiliza codigo.

Primeramente, permite introducir palabrar reservadas y que estas tenga un formato distinto al resto del texto. Se hace de la siguiente forma:

```markdown
La palabra `root` es una palabra reservada en el lenguaje SQL.
```

El resultado seria el siguiente:

La palabra `root` es una palabra reservada en el lenguaje SQL.


Por ultimo, en *Markdown* se pueden introducir fracciones de codigo como se ha hecho en este documento de la siguiente manera:

```markdown
```[lenguaje que se use]

## Esto es codigo markdown

\``` (No usar la  \, es para escapar los caracteres)
```