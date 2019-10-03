# mongodb-taller

# Comandos importantes:
## Mostrar bases de datos: 
```javascript
show dbs
```
## Usar una base de datos: 

Para hacer referencia a la base de datos en específico se utiliza el objecto ` db `, además esto nos permite crear una nueva y usarla.

```javascript
use database_name
```
La operación anterior permite crear una nueva base de datos con el nombre dado.

## Crear colección
```javascript
db.createCollection(name, attrs...)
```
Para mayor información sobre los atributos, consultar: [Referencia](https://docs.mongodb.com/manual/reference/method/db.createCollection/)

## Ver las collecciones de una base de datos:

El siguiente comando muestra el listado de los nombres de las collecciones dentro de una base de datos:

```javascript

db.getCollectionNames()

```

[Referencia oficial](https://docs.mongodb.com/manual/reference/method/db.getCollectionNames/)

## Insertar datos en colleción:

Para un único dato:

```javascript

var obj = {
 'id': 'galaxy'
};

db.products.insertOne(obj);
       
```
Otros parámetros que recibe esta función, [referencia](https://docs.mongodb.com/manual/reference/method/db.collection.insertOne/).


> Si el nombre de la colleción no existe, mongo crea la colleción e inserta el documento.  
 



Considerando el manejo de errores como funciones auxiliares:

```javascript
try {
   db.products.insertOne( { item: "card", qty: 15 } );
} catch (e) {
   print (e);
};


```


Para varios datos:

```javascript
 var myobj = [
    { name: 'John', address: 'Highway 71'},
    { name: 'Peter', address: 'Lowstreet 4'},
    { name: 'Amy', address: 'Apple st 652'},
    { name: 'Hannah', address: 'Mountain 21'},
    { name: 'Michael', address: 'Valley 345'},
    { name: 'Sandy', address: 'Ocean blvd 2'},
    { name: 'Betty', address: 'Green Grass 1'},
    { name: 'Richard', address: 'Sky st 331'},
    { name: 'Susan', address: 'One way 98'},
    { name: 'Vicky', address: 'Yellow Garden 2'},
    { name: 'Ben', address: 'Park Lane 38'},
    { name: 'William', address: 'Central st 954'},
    { name: 'Chuck', address: 'Main Road 989'},
    { name: 'Viola', address: 'Sideway 1633'}
  ];
db.clients.insertMany( myobj, <optional params> ) 
        


```

El atributo `_id`: Automático para mongo si el usuario no inserta alguno.

## Buscar datos:
 Buscar un dato: El siguiente comando retorna la primera ocurrencia del parámetro de búsqueda:
 
 ```javascript
  db.products.findOne({});
 ```
 
 Búsqueda con condiciones de selección:
 Se definen los atributos que deben de contener los documentos a encontrar.
  ```javascript
  db.products.findOne({ '_id':123 });
 ```
 Buscar varios datos:
 
 ```javascript
 db.products.find({},{'_id':1})
 
 ```
 
 Ordenar los datos: Dada una búsqueda mongo permite ordenar los valores bajo una serie de criterios.
 
 ```javascript
 db.products.find().sort({_id: -1})
 
 ```
 
 Limitar los resultados: Permite limitar la cantidad de resultados a un valor máximo esperado.
  ```javascript
 db.products.find().sort({_id: -1}).limit(2)

 ```
 
 Más criterios de búsqueda: Los comandos anteriores permiten realizar búsquedas sobre valores que son exactamente iguales a los criterios de búsqueda. Mongo ofrece otras alternativas para mostrar datos bajo criterios más complejos.
 
 
 Mayor que: Este forma permite buscar documentos cuyo atributo sea mayor que un parámetro dado.
  ```javascript
 db.products.find({_id:{$gt: 1000}})
 ```

Otras formas de búsqueda:
* Igual: `$eq`
* Mayor que: `$gt`
* Mayor o igual que: `$gte`
* Menor que: `$lt`
* Menor o igual que: `$lte`
* Not equal: `$ne`
* In: `$in`, es utilizado para encontrar datos dentro arreglos:
```javascript
db.products.find({comments: { $in : ['ok','not cool'] }   })

```

Operadores lógicos:
* AND
* OR
* NOT
* NOR
Ejemplo:`
```javascript
 db.products.find({$or: [ {qty:15 },{qty: {$lt:21}} ] }).sort({qty:-1})

```




## Actualizar datos

Función *save*, actualiza un documento si ya existe el `_id` proporcionado. Esta operación sobre escribe todo el documento.
```javascript

db.products.save({
    _id: 890,
    nombre: "Portátil Lenovo",
    cantidad: 25,
    precio: 750
})



```
Función `update` actualiza si encuentra datos con el criterio de búsqueda dado:  
```javascript

db.products.update({
    _id: ObjectId("51e64cd2403754f2073712da")
},
{
   
        cantidad: 35,
        precio: 60

})

```

La función set nos permite actualizar sólo los datos especificados, todos aquellos que no se mencionen no tendrán modificación alguna. 
 
 ```javascript
 
db.products.update({
    _id: ObjectId("51e64cd2403754f2073712da")
},
{
    $set: {
        cantidad: 35,
        precio: 60
    }
})


```
## Borrar datos:

## Eliminar primera ocurrencia:

```javascript
db.collection.remove( { query } );

```

## Eliminar varios documentos:


```javascript
db.collection.remove( { } );


```

## Funciones de agregación:
 
 
## Documentación oficial:

## MLAB:

## Conexión remota:
