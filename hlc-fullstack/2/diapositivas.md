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
- ### Introducción
- ### Bases de datos noSQL
- ### MongoDB: Primeros pasos
- ### MongoDB: Operaciones básicas
- ### MongoDB: Copias de seguridad

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



## MongoDB: Primeros pasos

![Mongo DB](assets/mongodb.png)


### Instalación

#### Ubuntu 18.04

```bash
apt update 
apt install mongodb  # se instala la versión 3.6.3
``` 


### Instalación

#### Ubuntu 16.04 y 14.04

- No instalaremos el paquete que viene en los repositorios.
- Se instalará el paquete mongodb-org, con una versión más actualizada.
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

**mongo   *nombre_bd***

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


### Cambiar de BD

**use *nombre_bd***

- Si la BD no existe, automáticamente se crea.

```bash
> use prueba
switched to db prueba
```


### db

**db**

- **db** es la variable que contiene el nombre de la BD en uso.

```bash
> db    
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


### BD de ejemplo

- De ahora en adelante, usaremos una BD llamada **agenda**.
- Dicha BD tendrá una colección de **personas**.

```bash
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



## MongoDB: Operaciones básicas


### Trabajar con documentos 

- **insert**: Insertar documentos
- **find**: Ver/Mostrar/Listar documentos
- **update**: Actualizar documentos
- **remove**: Eliminar documentos


### Comparativa de operaciones

CRUD      | Relacional  | MongoDB
----------|-------------|--------------
CREATE    | INSERT      | insert
READ      | SELECT      | find
UPDATE    | UPDATE      | update
DELETE    | DELETE      | remove 


### Crear documentos (objetos)

```bash
> var persona1 = {nombre: "Mario", apellido: "Neta"}
> var persona2 = {nombre: "Pere", apellido: "Gil", pais: "España"}
> persona1
{ "nombre" : "Mario", "apellido" : "Neta" }
> persona2
{ "nombre" : "Pere", "apellido" : "Gil", "pais" : "España" }
```


### Insertar documentos

**db.*nombre_colección*.insert ( ... )**

- Si la colección no existe, automáticamente se crea.
- A cada elemento se le asigna automáticamente un identificador único.
- Insertamos documentos uno a uno.

```bash
> db.personas.insert(persona1)
> db.personas.insert(persona2)
> db.personas.insert({nombre: "Elba", apellido: "Lazo", edad: 24})
```


### Insertar documentos

**db.*nombre_colección*.insert ( ... )**

- Es posible insertar **varios documentos de una vez**.
- Para ello insertamos un **array**.

```bash
> var p1 = { nombre: "Lola", apellido: "Mento", edad: 35 }
> var p2 = { nombre: "Encarna", apellido: "Vales", edad: 17, pais: "USA" }
> db.personas.insert( [p1, p2] )
```


### Ver documentos 

**db.*nombre_colección*.find( ... )**

```bash
> db.personas.find()  // equivale a `SELECT * FROM personas` en BD relacional
```


### Propiedades específicas

```bash
> db.personas.find({}, { nombre: 1, edad: 1, _id: 0 })
```


### Búsqueda condicional

- `$ne`: *not equal*
- `$gt`: *greater than*
- `$lt`: *less than*

```bash
> db.personas.find( { pais: "España"} )
> db.personas.find( { pais: {$ne: "España"} } )
> db.personas.find( { edad: {$gt: 18} } )
> db.personas.find( { edad: {$lt: 18} } )
```


### La función sort(...)

-  `1`: orden ascendente
- `-1`: orden descendente. 

```bash
> db.personas.find().sort( {apellido: -1} )
```


### La función limit(...)

- `limit()`: muestra un número máximo de documentos.

```bash
> db.personas.find().limit(2)
```


### La función skip(...)

- `skip()`: salta un número de documentos.

```bash
> db.personas.find().sort( {apellido: -1} ).skip(1)
```


### La función count()

- `count()`: indica el número de documentos totales encontrados.

```bash
> db.personas.find().sort( {apellido: 1} ).skip(1).count()  // 5
```


### La función size()

- `size()`: indica el número de documentos que se muestran.

```bash
> db.personas.find().sort( {apellido: 1} ).skip(1).size()  // 4
```


### Diferencia entre count() y size()

- `count()`
  - cuenta todos los documentos de la consulta. 
  - No tiene en cuenta a `skip()`, `limit()`, etc.
- `size()` 
  - cuenta los documentos mostrados. 
  - Sí tiene en cuenta a `skip()`, `limit()`, etc.

```bash
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).count()  // 5
> db.personas.find().sort( {apellido: 1} ).skip(1).limit(2).size()   // 2
```


### Ver un documento

**db.*nombre_colección*.findOne( ... )**

```bash
> db.personas.findOne()
{
	"_id" : ObjectId("58937be7a70c3985de49a38f"),
	"nombre" : "Mario",
	"apellido" : "Neta"
}
```


### Modificar documentos

```bash
> p = db.personas.findOne({ nombre: "Encarna" })
> p.edad = 18
> db.personas.update({ nombre: "Encarna" }, p)
```


### Modificar documentos

- `$set`: establece un valor  

```bash
> db.personas.update( { nombre: "Encarna" }, { $set: { edad: 19 } } )
```


### Modificar documentos

- `save()`:  

```bash
> var persona = db.personas.findOne({ "_id" : ObjectId("58938745a70c3985de49a392")})
> persona.nombre = "Salva"
> db.personas.save(persona)
```

Note: Cuidado al guardar el documento en una variable. Hay que usar `findOne()` ya que utilizando `find()` el valor de la variable se pierde. Otra opción es volcar el resultado de la consulta en un array con `find().toArray`.


### Eliminar documentos

```bash
> db.personas.remove({pais: "España"})
```



## MongoDB: Copias de seguridad


### Realizar copia de BD

**mongodump  -d  *nombre_bd***

- Se ejecuta desde el terminal de Linux, no desde la *shell* de MongoDB.
- Se crea directorio `dump` y dentro el diretorio *nombre_bd*, en este caso `agenda`. 
- Las colecciones de la base de datos se guardan en formato BSON. 

```bash
mongodump  -d  agenda
```


### Restaurar copia de BD
 
**mongorestore  -d  *nombre_bd*  dump/*nombre_bd*** 

- Se ejecuta desde el terminal de Linux, no desde la *shell* de MongoDB.

```bash
mongorestore  -d  agenda  dump/agenda
```
