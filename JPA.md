    CREATE DATABASE IF NOT EXISTS xxxxxxx DEFAULT CHARACTER SET utf8mb3 ;
    USE `xxxxxxx` ;



# Spring Data JPA

Luego de configurar el POM.xml para añadir la dependencia de JBDC se debe configurar la Base de Datos en el application.properties

![image](https://github.com/Pierohc/GTICS/assets/133728861/557568d0-66ae-4a20-941e-b86f5fa20e80)

Si sucede algún error adicionar la zona horaria y el uso de certificados SSL

- ?serverTimezone=America/Lima
- &useSSL=false&publicKeyRetrieval=true

![image](https://github.com/Pierohc/GTICS/assets/133728861/567dec6e-a328-43fe-be93-b7819df77e3f)
![image](https://github.com/Pierohc/GTICS/assets/133728861/b8198c93-a9d4-40f7-8deb-7c17292a8a6e)


Los pasos para usar el JDBC con Spring Data se resumen en armar las siguientes partes:

1. Entidades (Clases tipo Bean pero con mapeo en los atributos a la Base de Datos (Lombok))
2. Repositorios (Interfaces tipo DAO de tipo JpaRepository que funcionan como repositorios de métodos JPA)
3. Controladores (Se declara la Interfaz o interfaces de tipo repositorio a usar)


## Entidades

![image](https://github.com/Pierohc/GTICS/assets/133728861/fc34e100-3841-4257-b15c-2002f9013da8)
![image](https://github.com/Pierohc/GTICS/assets/133728861/6820c42e-ecf2-4e0d-82c0-a41e70413d81)

En caso no coincida el nombre de los atributos con los que están en la tabla de la base de datos se debe anotar con *@Column* el nombre de la columna en base de datos que hace referencia a dicho atributo.

*NOTA: Especificar nullable=false siempre y si es autoincremental anotar @GeneratedValue*

![image](https://github.com/Pierohc/GTICS/assets/133728861/10338b91-b7dc-4371-916e-ae2b815eaf8b)

*NOTA: Añadir en application.properties esta linea para no tener inconvenientes si se olvidó usar el CamelCase*
spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
![image](https://github.com/Pierohc/GTICS/assets/133728861/5ffc093d-254c-480a-9b21-69bbe0f66866)


## Repositorios

Para gestionar las entidades en Spring Data JPA, se deben crear repositorios (anteriormente los DAOS). Para crear un Repositorio, se crea un interfaz (Java Interface) que herede la clase JpaRepository (la más completa).

Cada interfaz maneja una entidad, se debe asociar correctamente:
![image](https://github.com/Pierohc/GTICS/assets/133728861/ed5f11ae-9a8c-4e49-88a6-b14e17ee1545)

## Controladores

En el controlador se debe definir el o los repositorios a utilizar para acceder a sus métodos que manejan las entidades que requiramos administrar:

![image](https://github.com/Pierohc/GTICS/assets/133728861/88a2b9b1-9de9-4d89-84dc-72feba21c857)


# Métodos JPA:

![image](https://github.com/Pierohc/GTICS/assets/133154904/4b7eceb3-04d4-458a-a935-9a9badff9d8a)

# Listar toda una tabla y enseñarla en consola: 

![image](https://github.com/Pierohc/GTICS/assets/133154904/2da7fadf-a1af-45fe-a56b-7ecaa9f85559)

## Ahora para mandarlo a la vista HTML desde el CONTROLLER:

![image](https://github.com/Pierohc/GTICS/assets/133154904/f1eea34b-0a3d-476d-805c-5e36e9b6c432)

El resultado se puede ver en la tabla usando th: each

![image](https://github.com/Pierohc/GTICS/assets/133154904/94923aba-7506-4eb4-8691-d36c6d28ad61)

![image](https://github.com/Pierohc/GTICS/assets/133154904/531533d5-1cc3-472b-a077-0f31a77a42ab)

--------------------------------------------------------------------------------------------------------------------

# Crear un nuevo Objeto (transportista para este caso):

![image](https://github.com/Pierohc/GTICS/assets/133154904/6bbd96bf-1cc6-4629-be48-74ebbae5398d)

![image](https://github.com/Pierohc/GTICS/assets/133154904/8bd3e837-cdc9-4ddf-8ce3-3d26c2b0b757)

## Mandar los datos ingresados por POST al CONTROLLER(Para este caso se usa DATA BINDING):

![image](https://github.com/Pierohc/GTICS/assets/133154904/e5be6e30-5ddf-4190-ac60-7f530308712c)

## Guardar en DB el nuevo transportista: 

![image](https://github.com/Pierohc/GTICS/assets/133154904/8463acd1-8773-40ca-abda-cb697439082c)


--------------------------------------------------------------------------------------------------------------------


### Editar con JPA

Se realiza mediante ID (primary key) Por lo tanto, se debe gestionar la ruta /editar, con un parámetro por get, en este caso, el ID.

![image](https://github.com/Pierohc/GTICS/assets/133728861/a6b5840a-c0ee-4a1a-ad5f-0fe840ef92bc)

Primero se debe buscar el Transportista en base al ID recibido por GET, para este fin, se usa el método findById del repositorio.
Este método devuelve un objeto del tipo Optional. ¿Y qué es el objeto tipo Optional?

A partir de java 8 se incluyó la clase “Optional”, la cual permite validar si existe un valor de retorno o no por medio del método .isPresent(). En caso se haya obtenido un valor de la base de datos, podemos recuperar el objeto (en este caso Shipper), por medio del método get(). 

![image](https://github.com/Pierohc/GTICS/assets/133728861/94b3f5dd-2090-44f1-b1a6-a3c8f3760b3f)

Una vez se ha comprobado que existe podemos redirigir al usuario al form para introducir los nuevos datos:

![image](https://github.com/Pierohc/GTICS/assets/133728861/a2ad57e9-1013-4d2f-964f-c083117c5167)

Para actualizar un registro se vuelve a usar la misma ruta, esto se debe a que Spring Data JPA utiliza el mismo método para guardar un nuevo registro y para actualizarlo → save().
¿Y cómo diferencia si está guardando o editando? Si el formulario contiene un ID, y este se asigna al objeto por el dataBinding, entonces Spring actualiza. Si no encuentra un ID en el objeto a guardar, entonces guarda un nuevo registro.
Observar que en el formulario de edición se tiene un input oculto (hidden) con el ID del Transportista

![image](https://github.com/Pierohc/GTICS/assets/133728861/20594abd-5cad-44c7-b605-7b4bd14c7738)

### Redirección en Spring MVC

Para redireccionar en Spring mvc (entre controladores), se pueden usar los métodos:
- redirect: 
  - cambia el URL
  - genera un nuevo GET (le responde al usuario con un 302 y el realiza una nueva solicitud)
- forward:
  - no cambia el URL
  - la redirección es interna en el servidor, no se genera un nuevo GET.

### Borrar con JPA

De nuevo se realiza mediante el ID de la entidad (primary key). Por lo tanto, se debe gestionar la ruta /borrar, con un parámetro por get, en este caso, el ID.

![image](https://github.com/Pierohc/GTICS/assets/133728861/12a96afd-4133-4f91-a8ca-28d96e72b42f)

En el contralor, primero se debe buscar el shipper por el ID que se ha recibido.  Para este fin, se utiliza el método findById( ) del repositorio (el mismo que para la edición).
Luego, si se encuentra el objeto, se procede a borrarlo con el método deleteById( ).

![image](https://github.com/Pierohc/GTICS/assets/133728861/1f24b0b5-d43c-48c2-844d-40c67a5eaca2)

JpaRepository contiene 3 métodos para borrar:
- DeleteById: borra un elemento por su ID
- DeleteAll: borra todos los elementos de una tabla uno por uno
- DeleteAllInBatch: borra todos los elementos de una tabla en una sola sentencia

## Otras Funciones

![image](https://github.com/Pierohc/GTICS/assets/133728861/c2227ed0-252d-461f-a3bc-e8618b83060d)

