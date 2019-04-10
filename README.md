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

<div style="
  min-width: 250px; 
  margin-left: -125px; 
  background-color: #333;
  color: #fff; 
  text-align: center; 
  border-radius: 2px;
  padding: 16px;
  position: fixed; 
  left: 50%; 
  bottom: 30px; "> 
  

  Si el nombre de la colleción no existe, mongo crea la colleción e inserta el documento.  
 </div>



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
db.products.insertOne( obj, <optional params> ) 
        


```

El atributo `_id`:

## Buscar datos:
 Buscar un dato:
 
 Buscar varios datos:
 
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
