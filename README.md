# mongodb-taller

# Comandos importantes:
## Mostrar bases de datos: 
```javascript
show dbs
```
## Usar una base de datos: 

Para hacer referencia a la base de datos en específico se utiliza el objecto ` db `

```javascript
use database_name
```

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
 
 Ordenar los datos:
 
 ```javascript
 
 ```
 
 Limitar los resultados:
  ```javascript
 
 ```
 
 Más criterios de búsqueda:
  ```javascript
 
 ```
 
 Mayor que:
  ```javascript
 
 ```
 Menor que:
  ```javascript
 
 ```
 
 Mayor o igual que:
  ```javascript
 
 ```
 
 Menor o igual que:
  ```javascript
 
 ```
 
 
 
## Borrar datos:

## Eliminar primera ocurrencia:

```javascript

```

## Eliminar varios documentos:


```javascript

```

## Funciones de agregación:
 
 
## Documentación oficial:

## MLAB:

## Conexión remota:
