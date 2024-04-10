
# Spring Data JPA

Luego de configurar el POM.xml para añadir la dependencia de JBDC y LOMBOK se debe configurar la Base de Datos en el application.properties

![image](https://github.com/Pierohc/GTICS/assets/133728861/557568d0-66ae-4a20-941e-b86f5fa20e80)

Si sucede algún error adicionar la zona horaria y el uso de certificados SSL

- ?serverTimezone=America/Lima
- &useSSL=false&publicKeyRetrieval=true

![image](https://github.com/Pierohc/GTICS/assets/133728861/567dec6e-a328-43fe-be93-b7819df77e3f)
![image](https://github.com/Pierohc/GTICS/assets/133728861/b8198c93-a9d4-40f7-8deb-7c17292a8a6e)



*NOTA: RECORDAR USAR CAMELCASE Y COLOCAR EN EL application.properties*
spring.jpa.hibernate.naming.physical-strategy=org.hibernate.boot.model.naming.PhysicalNamingStrategyStandardImpl
![image](https://github.com/Pierohc/GTICS/assets/133728861/5ffc093d-254c-480a-9b21-69bbe0f66866)


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



