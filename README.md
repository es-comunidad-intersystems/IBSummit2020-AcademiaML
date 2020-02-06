# Academia ML con InterSystems IRIS

Esta academia muestra como se puede trabajar con tecnologías de Aprendizaje máquina (Machine Learning o ML) en conjunción con la plataforma de datos IRIS, y operacionalizar (poner en producción) algoritmos ML sobre la plataforma para su uso en tiempo real.



Esta academia muestra como:

- Acceder a IRIS desde entornos ML (Python y Jupyter Notebook)

- Operacionalizar algoritmos de ML con PMML

- Interactuar con Python desde InterSystems IRIS con el Python Gateway

- La construcción automatizada de algoritmos ML mediante comandos SQL simples

  

## ¿Qué necesitas? 

* [Git](https://git-scm.com/downloads) 
* [Docker](https://www.docker.com/products/docker-desktop)
* [Docker Compose](https://docs.docker.com/compose/install/)
* [Postman](https://www.getpostman.com/downloads/)https://docs.docker.com/compose/install/)
* [DBeaver](https://dbeaver.io/download/)

## Instalación



### Descargar código

```console
$git clone https://github.com/PYDuquesnoy/irismlacademy
```



### Decargar los contenedores docker

```console
$docker-compose pull
```



### Configurar la Conexión JDBC en DBeaver

En DBeaver,  definir el driver JDBC de Intersystems IRIS en el Menu "Database" / "Driver Manager":

| Campo        | Valor                                           |
| ------------ | ----------------------------------------------- |
| Driver name  | IRIS                                            |
| Driver Type  | Generic                                         |
| ClassName    | com.intersystems.jdbc.IRISDriver                |
| URL Template | jdbc://IRIS://{host}:{port}/{database}          |
| Default Port | 51773                                           |
| Description  | InterSystems IRIS JDBC Driver                   |
| Libraries    | irismlacademy/shared/intersytems-jdbc-3.1.0.jar |
| Driver Class | com.intersystems.jdbc.IRISDriver                |



Definir la conexión JDBC al contenedor iris4ml:

| Campo     | Valor     |
| --------- | --------- |
| host      | localhost |
| port      | 51773     |
| Database  | MLACADEMY |
| User name | SuperUser |
| Password  | sys       |



## Verificar la instalación

Arrancar los 2 contenedores:

```console
$docker-compose up
```
Desde un Browser, verifica que se puede acceder a ambos contenedores, la plataforma InterSystems IRIS y el notebook jupyter:

| Contenedor       | URL                                         | usuario   | password |
| ---------------- | ------------------------------------------- | --------- | -------- |
| iris4ml          | http://localhost:52773/csp/sys/UtilHome.csp | SuperUser | sys      |
| jupyter notebook | http://locahost.8888                        | -         | IRIS     |

​	
​	