<!---
Ejemplos de inserción de videos

<video class="stretch" controls><source src="http://clips.vorwaerts-gmbh.de/big_buck_bunny.mp4" type="video/mp4"></video>
<iframe width="560" height="315" src="https://www.youtube.com/embed/3RBq-WlL4cU" frameborder="0" allowfullscreen></iframe>

slide: data-background="#ff0000" 
element: class="fragment" data-fragment-index="1"
-->

## HLC - Fullstack
---
![HLC-Fullstack](http://jamj2000.github.io/hlc-fullstack/hlc-fullstack.png)
<small> 2018-19 - IES Luis Vélez de Guevara - Écija - Spain </small>


## Bases de Datos noSQL

[![cc-by-sa](http://jamj2000.github.io/hlc-fullstack/cc-by-sa.png)](http://creativecommons.org/licenses/by-sa/4.0/)


## Índice
--- 
### Introducción
### Bases de datos noSQL
### MongoDB
### Operaciones básicas
### Copias de seguridad

<!--- Note: Nota a pie de página. -->



## Introducción


### En esta Unidad aprenderemos a

- Instalar el sistema gestor de bases de datos noSQL.
- Gestionar el sistema gestor de bases de datos noSQL.
- Distinguir los conceptos de base de datos, colección y documento.
- Realizar consultas de lectura y modificación de datos.
- Realizar y restaurar copias de seguridad de los datos.



## Bases de datos noSQL


### Características

- Muy eficientes.   
- Datos no consitentes en todo momento.
- Puede servir gran cantidad de carga de lecturas y escrituras.
- Esquema dinámico.


### Ventajas

- Permiten escalabilidad horizontal de forma sencilla.
- Se ejecutan en clusters de máquinas baratas.
- Pueden manejar enormes cantidades de datos.
- No generan cuellos de botella.


### Desventajas

- Tecnología relativamente nueva.
- Para datos que siguen el modelo relacional son mejores los SGBDR.
- Poca cantidad de desarrolladores y administradores que conocen la tecnología.
- Falta de estándares. Cada base de datos NoSQL tiene su propia API.



## MongoDB


### Instalación

- En Ubuntu 18.04:
  ```bash
  apt update 
  apt install mongodb  # se instala la versión 3.6.3
  ``` 


### Instalación

- En distribuciones más antiguas, la versión que viene en los repositorios está anticuada.
- En Ubuntu 16.04 y 14.04:
  - No instalaremos el paquete que viene en los repositorios.
  - Sino que seguiremos los pasos indicados en https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/.
  - Se instalará el paquete mongodb-org, con un versión más actualizada.


### Servicio

- Ver estado del servicio: `systemctl  status  mongodb`
- Iniciar el servicio: `systemctl  start  mongodb`
- Reiniciar el servicio: `systemctl  restart  mongodb`
- Parar el servicio: `systemctl  stop  mongodb`

- Habilitar en el inicio: `systemctl  enable  mongodb`
- Deshabilitar en el inicio: `systemctl  disable  mongodb`


### Servidor y cliente 

- Servidor: `mongod`
- Cliente: `mongo`

```bash
mongod  --version
mongo   --version
```


### Conectar al gestor de BBDD

**`mongo`**
**`mongo  nombre_bd`**

- Ejemplo 1:
  ```bash
  $ mongo 
  connecting to: test
  MongoDB shell version: 3.2.21
  ```
- Ejemplo 2:
  ```bash
  $ mongo local
  connecting to: local
  MongoDB shell version: 3.2.21
  ```


### Listar BBDD

**`show databases`**

  ```bash
  > show databases;
  admin  0.000GB
  local  0.000GB
  ```


### Usar/Crear una BD

**`use nombre_bd`**

- Si la BD no existe, entonces se crea.
- Ejemplo:
  ```bash
  > use prueba
  switched to db prueba
  ```


### Ver la BD en uso

**`db`**

- Ejemplo:
  ```bash
  > db    //la variable db contiene el nombre de la BD en uso
  prueba
  ```


### Eliminar una BD

**`db.dropDatabase()`**

- Ejemplo:
  ```bash
  > db.dropDatabase()
  { "ok" : 1 }
  ```


### Colecciones y Documentos

- Una colección es el *equivalente* noSQL a una tabla relacional.
- Una colección se compone de documentos (objetos).
- Un documento es el *equivalente* noSQL a un registro o fila en una tabla relacional.
- Un documento se compone de propiedades.


### Comparativa de términos 

Relacional       | noSQL
-----------------|--------------
Base de datos    | Base de datos
Tabla            | Colección
Registro o fila  | Documento (objeto)
Campo            | Propiedad


### BD de pruebas

- De ahora en adelante, usaremos una BD llamada `agenda`.
- Dicha BD almacenará documentos de personas.
- Para crear dicha BD escribiremos `use agenda`.


### Listar colecciones de la BD en uso

**`show collections`**

- Ejemplo
  ```bash
  > show collections
  personas
  tareas
  ```

Note: 


## Operaciones básicas


### Trabajar con documentos 

- **insert**: Insertar documentos
- **find**: Ver/Mostrar/Listar documentos
- **update**: Actualizar documentos
- **remove**: Eliminar documentos


### Comparativa de operaciones

CRUD      | Relacional  | noSQL
----------|-------------|--------------
CREATE    | INSERT      | insert
READ      | SELECT      | find
UPDATE    | UPDATE      | update
DELETE    | DELETE      | remove 


### Crear objetos (documentos)

```console
> var persona1 = {nombre: "Mario", apellido: "Neta"}
> var persona2 = {nombre: "Pere", apellido: "Gil", pais: "España"}
> persona1
{ "nombre" : "Mario", "apellido" : "Neta" }
> persona2
{ "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
```


### Insertar documentos

`db.nombre_coleccion.insert ( ... )`

- Si la colección no existe, entonces se crea.
- Ejemplo:
  ```bash
  > db.personas.insert(persona1)
  WriteResult({ "nInserted" : 1 })
  > db.personas.insert(persona2)
  WriteResult({ "nInserted" : 1 })
  > db.personas.insert({nombre: "Elba", apellido: "Lazo", edad: 24})
  WriteResult({ "nInserted" : 1 })
  ```


### Insertar varios documentos al mismo tiempo

`db.nombre_coleccion.insert ( ... )`

- En lugar de insertar un sólo documento, insertamos un array.
- Ejemplo:
  ```console
  > var p1 = { nombre: "Lola", apellido: "Mento", edad: 35 }
  > var p2 = { nombre: "Encarna", apellido: "Vales", edad: 17, pais: "USA" }
  > db.personas.insert( [p1, p2] )
  ```


### Listar documentos 

**`db.nombre_coleccion.find( ... )`**

- A cada elemento insertado se le asigna de forma automática un identificador único.
- Ejemplo:
  ```console
  > db.personas.find()  // equivalente a `SELECT * FROM personas` en BD relacional
  { "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
  { "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
  { "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
  { "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
  { "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
  ```


### Ver un solo documento

**`db.nombre_coleccion.findOne( ... )`**

```console
> db.personas.findOne()
{
	"_id" : ObjectId("58937be7a70c3985de49a38f"),
	"nombre" : "Mario",
	"apellido" : "Neta"
}
```

### Búsqueda condicional I

```console
> db.personas.find({nombre: "Elba"})
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
> 
> db.personas.find({pais: "España"})
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
```

### Búsqueda condicional II

`$ne` significa *not equal*, `$gt` es *greater than* y `$lt` es *less than*.

```console
> db.personas.find( { pais: {$ne: "España"} } )
{ "_id" : ObjectId("5b91a55cc09f7d7243295719"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("5b91a5abc09f7d724329571c"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("5b91a5b8c09f7d724329571d"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("5b91a5c6c09f7d724329571e"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
> 
> db.personas.find( { edad: {$gt: 18} } )
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre": "Lola", "apellido": "Mento", "edad": 35 }
> 
> db.personas.find( { edad: {$lt: 18} } )
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre": "Encarna", "apellido": "Vales", "edad": 17, "pais": "USA" }
```


### Consultar un número concreto de campos

Vamos a mostrar un listado de los personas solo con los campos `nombre` y `edad`.

```console
> db.personas.find({}, {nombre: 1, edad: 1, _id:0})
{ "nombre" : "Mario" }
{ "nombre" : "Elba", "edad" : 24 }
{ "nombre" : "Salva", "edad" : 35 }
{ "nombre" : "Lola", "edad": 35 }
{ "nombre" : "Encarna", "edad": 17 } 
```


### Contar documentos

```console
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
> 
> db.personas.find().count()
4
```

### Consultas ordenadas

El valor `1` se utiliza para realizar una consulta en orden ascendente y el `-1` para descendente. Con `limit()` se puede limitar el resultado a un número máximo de documentos.

```console
> db.personas.find().sort( {apellido: 1} )
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
> 
> db.personas.find().sort( {apellido: -1} )
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
> 
> db.personas.find().sort( {apellido: -1} ).limit(3)
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
```


### La función `skip()`

La función `skip()` permite "saltar" un número determinado de documentos de la consulta.

```console
> db.personas.find().sort( {apellido: 1} ).limit(2)
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
> 
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2)
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
```

### La función `size()`

A diferencia de `count()`, el método `size()` ofrece la cuenta de la consulta una vez filtrada con `skip()`, `limit()`, etc.

```console
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).count()
4
> 
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).size()
2
```

### Agrupación de documentos

Antes de hacer pruebas con la agrupación de documentos, vamos a meter más datos en nuestra colección de personas.

```console
> db.personas.insert({nombre: "Elsa", apellido: "Pato", edad: 52, pais: "Portugal"})
WriteResult({ "nInserted" : 1 })
> db.personas.insert({nombre: "Armando", apellido: "Bronca", edad: 22, pais: "Francia"})
WriteResult({ "nInserted" : 1 })
> db.personas.insert({nombre: "Leandro", apellido: "Gado", edad: 48, pais: "Venezuela"})
WriteResult({ "nInserted" : 1 })
> db.personas.insert({nombre: "Olga", apellido: "Seosa", edad: 29, pais: "España"})
WriteResult({ "nInserted" : 1 })
> db.personas.insert({nombre: "Elena", apellido: "Nito", edad: 30, pais: "USA"})
WriteResult({ "nInserted" : 1 })
> 
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
{ "_id" : ObjectId("5895b74415c260814ec7f139"), "nombre" : "Elsa", "apellido" : "Pato", "edad" : 52, "pais" : "Portugal" }
{ "_id" : ObjectId("5895b77215c260814ec7f13a"), "nombre" : "Armando", "apellido" : "Bronca", "edad" : 22, "pais" : "Francia" }
{ "_id" : ObjectId("5895b7d915c260814ec7f13b"), "nombre" : "Leandro", "apellido" : "Gado", "edad" : 48, "pais" : "Venezuela" }
{ "_id" : ObjectId("5895b88815c260814ec7f13c"), "nombre" : "Olga", "apellido" : "Seosa", "edad" : 29, "pais" : "España" }
{ "_id" : ObjectId("5895b8ab15c260814ec7f13d"), "nombre" : "Elena", "apellido" : "Nito", "edad" : 30, "pais" : "USA" }
```

Vamos a mostrar todos los países de donde son los personas.

```console
> db.personas.aggregate( [ {$group: {_id: "$pais"}} ] )
{ "_id" : "Venezuela" }
{ "_id" : "Francia" }
{ "_id" : null }
{ "_id" : "España" }
{ "_id" : "USA" }
{ "_id" : "Portugal" }
```

Ahora igual pero diciendo cuántas veces se repite cada pais.

```console
> db.personas.aggregate( [ {$group: {_id: "$pais", repetidos: {$sum: 1}}} ] )
{ "_id" : "Venezuela", "repetidos" : 1 }
{ "_id" : "Francia", "repetidos" : 1 }
{ "_id" : null, "repetidos" : 3 }
{ "_id" : "España", "repetidos" : 2 }
{ "_id" : "USA", "repetidos" : 2 }
{ "_id" : "Portugal", "repetidos" : 1 }
```

Igual y además con la media de edad por pais.

```console
> db.personas.aggregate( [ {$group: {_id: "$pais", repetidos: {$sum: 1}, "edad media": {$avg: "$edad"}}} ] )
{ "_id" : "Venezuela", "repetidos" : 1, "edad media" : 48 }
{ "_id" : "Francia", "repetidos" : 1, "edad media" : 22 }
{ "_id" : null, "repetidos" : 3, "edad media" : 29.5 }
{ "_id" : "España", "repetidos" : 2, "edad media" : 29 }
{ "_id" : "USA", "repetidos" : 2, "edad media" : 23.5 }
{ "_id" : "Portugal", "repetidos" : 1, "edad media" : 52 }
```

Igual que todo lo anterior y además excluyendo los valores `null` para el atributo `pais`.

```console
> db.personas.aggregate( [ {$match: {pais: {$ne: null}}}, {$group: {_id: "$pais", repetidos: {$sum: 1}, "edad media": {$avg: "$edad"}}} ])
{ "_id" : "Venezuela", "repetidos" : 1, "edad media" : 48 }
{ "_id" : "España", "repetidos" : 2, "edad media" : 29 }
{ "_id" : "USA", "repetidos" : 2, "edad media" : 23.5 }
{ "_id" : "Portugal", "repetidos" : 1, "edad media" : 52 }
{ "_id" : "Francia", "repetidos" : 1, "edad media" : 22 }
```


### Consultas con expresiones regulares

Vamos a mostrar todos los personas cuyos apellidos contienen la letra "e".

```console
> db.personas.find( {apellido: /e/} )
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
{ "_id" : ObjectId("5895b88815c260814ec7f13c"), "nombre" : "Olga", "apellido" : "Seosa", "edad" : 29, "pais" : "España" }
```

personas cuyo nombre termina con la cadena "na".

```console
> db.personas.find( {nombre: /na$/} )
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
{ "_id" : ObjectId("5895b8ab15c260814ec7f13d"), "nombre" : "Elena", "apellido" : "Nito", "edad" : 30, "pais" : "USA" }
```

personas cuyo nombre comienza por "El".

```console
> db.personas.find( {nombre: /^El/} )
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("5895b74415c260814ec7f139"), "nombre" : "Elsa", "apellido" : "Pato", "edad" : 52, "pais" : "Portugal" }
{ "_id" : ObjectId("5895b8ab15c260814ec7f13d"), "nombre" : "Elena", "apellido" : "Nito", "edad" : 30, "pais" : "USA" }
> 
```


### Edición de un documento con `update()`

Vamos a modificar la edad de la persona cuyo nombre es `Encarna`.

```console
> p = db.personas.findOne({nombre: "Encarna"})
{
	"_id" : ObjectId("58938745a70c3985de49a393"),
	"nombre" : "Encarna",
	"apellido" : "Vales",
	"edad" : 17,
	"pais" : "USA"
}
> p.edad = 18
18
> db.personas.update({nombre: "Encarna"}, p)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.personas.find({nombre: "Encarna"})
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 18, "pais" : "USA" }
```


### Edición de un documento con `update()` y `$set`

De nuevo vamos a modificar la edad de `Encarna`.

```console
> db.personas.update( {nombre: "Encarna"}, {$set: {edad: 19} } )
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.personas.find({nombre: "Encarna"})
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
```


### Edición de un documento con `save()`

```console
> var persona = db.personas.findOne({ "_id" : ObjectId("58938745a70c3985de49a392")})
> persona
{
	"_id" : ObjectId("58938745a70c3985de49a392"),
	"nombre" : "Lola",
	"apellido" : "Mento",
	"edad" : 35
}
> persona.nombre = "Salva"
Salva
> persona
{
	"_id" : ObjectId("58938745a70c3985de49a392"),
	"nombre" : "Salva",
	"apellido" : "Mento",
	"edad" : 35
}
> db.personas.save(persona)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
```

:warning: Cuidado al guardar el documento en una variable. Hay que usar `findOne()` ya que utilizando `find()` el valor de la variable se pierde. Otra opción es volcar el resultado de la consulta en un array con `find().toArray`.


### Eliminar documentos

Vamos a eliminar todos los personas cuyo atributo `pais` sea `España`.

```console
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
> 
> db.personas.remove({pais: "España"})
WriteResult({ "nRemoved" : 1 })
> 
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Salva", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }

```


## Copias de seguridad


### Realizar copia de seguridad de una BD

**`mongodump  -d  nombre_bd`**

- El comando `mongodump` se ejecuta desde el terminal de Linux, no desde la *shell* de MongoDB.
- Dentro de `dump` se crea otro directorio con el nombre de la base de datos, en este caso `agenda`. 
- Dentro de este último directorio se guardan las colecciones de la base de datos en formato BSON. 
- Ejemplo:
  ```console
  $ mongodump -d agenda
  ```

### Restaurar copia de seguridad de una BD
 
**`mongorestore  -d  nombre_bd  dump/nombre_bd`** 

- Ejemplo:
  ```console
  $ mongorestore -d agenda dump/agenda
  ```






