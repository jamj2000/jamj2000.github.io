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

#### Ubuntu 18.04:

```bash
apt update 
apt install mongodb  # se instala la versión 3.6.3
``` 


### Instalación

### Ubuntu 16.04 y 14.04:

- No instalaremos el paquete que viene en los repositorios.
- Se instalará el paquete mongodb-org, con un versión más actualizada.
- Seguiremos los pasos indicados en https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/.


### Servicio

```bash
systemctl  status   mongodb   # Estado 
systemctl  start    mongodb   # Iniciar
systemctl  restart  mongodb   # Reiniciar
systemctl  stop     mongodb   # Parar

systemctl  enable   mongodb   # Habilitar
systemctl  disable  mongodb   # Deshabilitar
```


### Servidor y cliente 

- **mongod**: servidor
- **mongo**: cliente

```bash
mongod  --version
mongo   --version
```


### Conectar al gestor de BBDD

**mongo**

```bash
$ mongo 
connecting to: test
MongoDB shell version: 3.2.21
```

**mongo  *nombre_bd***

```bash
$ mongo local
connecting to: local
MongoDB shell version: 3.2.21
```


### Listar BBDD

**show databases**

```bash
> show databases;
admin  0.000GB
local  0.000GB
```


### Usar/Crear una BD

**use *nombre_bd***

Si la BD no existe, entonces se crea.

```bash
> use prueba
switched to db prueba
```


### Ver la BD en uso

**db**

```bash
> db    //Esta variable contine el nombre de la BD en uso
prueba
```


### Eliminar una BD

**db.dropDatabase()**

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

- De ahora en adelante, usaremos una BD llamada **agenda**.
- Dicha BD almacenará documentos de **personas**.

```mongo
> use agenda
switched to db agenda
```


### Listar colecciones de la BD en uso

**show collections**

```bash
> show collections
personas
tareas
```

Note: Aunque en el ejemplo aparecen 2 colecciones, a tí no debería aparecerte ninguna todavía.  


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

```bash
> var persona1 = {nombre: "Mario", apellido: "Neta"}
> var persona2 = {nombre: "Pere", apellido: "Gil", pais: "España"}
> persona1
{ "nombre" : "Mario", "apellido" : "Neta" }
> persona2
{ "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
```


### Insertar documentos

**db.*nombre_coleccion*.insert ( ... )**

Si la colección no existe, entonces se crea.

```bash
> db.personas.insert(persona1)
WriteResult({ "nInserted" : 1 })
> db.personas.insert(persona2)
WriteResult({ "nInserted" : 1 })
> db.personas.insert({nombre: "Elba", apellido: "Lazo", edad: 24})
WriteResult({ "nInserted" : 1 })
```


### Insertar varios documentos de una vez

**`db.nombre_coleccion.insert ( ... )`**

En lugar de insertar un sólo documento, insertamos un array.

```bash
> var p1 = { nombre: "Lola", apellido: "Mento", edad: 35 }
> var p2 = { nombre: "Encarna", apellido: "Vales", edad: 17, pais: "USA" }
> db.personas.insert( [p1, p2] )
```


### Listar documentos 

**`db.nombre_coleccion.find( ... )`**

A cada elemento insertado se le asigna de forma automática un identificador único.

```bash
> db.personas.find()  // equivalente a `SELECT * FROM personas` en BD relacional
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
```


### Ver un solo documento

**`db.nombre_coleccion.findOne( ... )`**

```bash
> db.personas.findOne()
{
	"_id" : ObjectId("58937be7a70c3985de49a38f"),
	"nombre" : "Mario",
	"apellido" : "Neta"
}
```


### Búsqueda condicional I

```bash
> db.personas.find({nombre: "Elba"})
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
> 
> db.personas.find({pais: "España"})
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
```


### Búsqueda condicional II

`$ne` significa *not equal*, `$gt` es *greater than* y `$lt` es *less than*.

```bash
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

```bash
> db.personas.find({}, {nombre: 1, edad: 1, _id:0})
{ "nombre" : "Mario" }
{ "nombre" : "Pere" }
{ "nombre" : "Elba", "edad" : 24 }
{ "nombre" : "Lola", "edad": 35 }
{ "nombre" : "Encarna", "edad": 17 } 
```


### Contar documentos

```bash
> db.personas.find()
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58937beca70c3985de49a390"), "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
> 
> db.personas.find().count()
5
```


### Consultas ordenadas

El valor `1` se utiliza para realizar una consulta en orden ascendente y el `-1` para descendente. 

Con `limit()` se puede limitar el resultado a un número máximo de documentos.

```bash
> db.personas.find().sort( {apellido: -1} ).limit(4)
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 17, "pais" : "USA" }
{ "_id" : ObjectId("58937be7a70c3985de49a38f"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("58938745a70c3985de49a392"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
{ "_id" : ObjectId("58937c23a70c3985de49a391"), "nombre" : "Elba", "apellido" : "Lazo", "edad" : 24 }
```


### La función `skip()`

La función `skip()` permite "saltar" un número determinado de documentos de la consulta.

```bash
> db.personas.find().sort( {apellido: -1} ).skip(1).limit(2)
{ "_id" : ObjectId("5b92dbe0b55c8a3a0d8651cf"), "nombre" : "Mario", "apellido" : "Neta" }
{ "_id" : ObjectId("5b92dc2b1ab0370cf4d942d9"), "nombre" : "Lola", "apellido" : "Mento", "edad" : 35 }
```


### La función `size()`

A diferencia de `count()`, el método `size()` ofrece la cuenta de la consulta una vez filtrada con `skip()`, `limit()`, etc.

```bash
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).count()
5
> 
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).size()
2
```


### Edición de un documento con `update()`

Vamos a modificar la edad de la persona cuyo nombre es `Encarna`.

```bash
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

```bash
> db.personas.update( {nombre: "Encarna"}, {$set: {edad: 19} } )
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })
> db.personas.find({nombre: "Encarna"})
{ "_id" : ObjectId("58938745a70c3985de49a393"), "nombre" : "Encarna", "apellido" : "Vales", "edad" : 19, "pais" : "USA" }
```


### Edición de un documento con `save()`

```bash
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

Note: Cuidado al guardar el documento en una variable. Hay que usar `findOne()` ya que utilizando `find()` el valor de la variable se pierde. Otra opción es volcar el resultado de la consulta en un array con `find().toArray`.


### Eliminar documentos

Vamos a eliminar todas las personas cuyo atributo `pais` sea `España`.

```bash
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

**mongodump  -d  *nombre_bd***

- Se ejecuta desde el terminal de Linux, no desde la *shell* de MongoDB.
- Se crea directorio `dump` y dentro el diretorio *nombre_bd*, en este caso `agenda`. 
- Las colecciones de la base de datos en formato BSON. 

```bash
mongodump  -d  agenda
```


### Restaurar copia de seguridad de una BD
 
**mongorestore  -d  *nombre_bd*  dump/*nombre_bd*** 

```bash
mongorestore  -d  agenda  dump/agenda
```