# Corte2_1075287060
# Control Alquiler Automóvil. 

#### Necesidad:  

Se debe desarrollar un sistema que permita tener todos los registros de cierta información para tener el control total de todos los automóviles y clientes; por lo cual simplemente se mostrara los automóviles disponibles
Categoría `Id`, `Nombre`, `Categoría`, `Descripción`, `Precio Por Días`. 
Automóvil `Id`, `Gama`, `Lugar de Recogida`, `Lugar de Devolución`, `Dia de recogida`, `Dia de Devolución`, `Hora de recogida`, `Hora de Devolución`.
Persona `Id`, `Nombre Completo`, `Id Tipo`, `Id Numero`, `Edad`, `Genero`, `Id WhatsApp`, `Email`.
Auto Persona `Id`, `Cliente`, `Método de Pago`, `Referencia Automóvil`, `Referencia Cliente`, `Valor Incluido`, `Total por Dia`.

#### Análisis: Definición de requerimientos:

Categoría Categoría {Id, Nombre, Descripción, Tarifa Diaria}
Automóvil Automóvil {Id, Gama, Color, Kilometraje, Estado}
Persona {Id, Nombre Completo, Id Tipo, Id Numero, Edad, Genero, Id WhatsApp, Email}
AutoPersona {Id, cliente, ref:Autos, ref:persona} 

##### Referencias Funcionales
1. RF1: Realizar CRUD de Categoría, donde requerirá la siguiente estructura en la entidad: `Categoría {Id, Nombre, Descripción, Tarifa Diaria}. `

2. RF2: Realizar la CRUD de Automóvil, donde requerir la siguiente estructura: `Automóvil {Id, Gama, Color, Kilometraje, Estado }. `

3. RF3: Realizar la CRUD de Persona, donde requiera la siguiente estructura: ` Persona {Id, Nombre Completo, Tipo Identidad, Numero Identidad, Edad, Genero, Id WhatsApp, Email}.`

4. RF4: Realizar la CRUD de AutosPersona, donde requiera la siguiente estructura: `{Id, cliente, ref:Autos, ref:persona}.`

5. RF5: El istema permitira eliminar, actualizar, regitrar nueva informacion tanto de los Clientes como de los Automóviles.

#### Referencias No Funcionales
1. RNF1: El sistema debe ser capaz de manejar un alto volumen de datos y usuarios sin comprometer su rendimiento.

2. RNF1: El sistema debe estar disponible para los usuarios la mayor cantidad de tiempo posible, con un mínimo de interrupciones o tiempos de inactividad.

3. RNF1: Los datos de los clientes, como la información personal y financiera, deben ser protegidos contra accesos no autorizados.

4. RNF: El sistema debe estar protegido contra ataques cibernéticos y otras amenazas de seguridad.

5. RNF: El sistema debe tener mecanismos para recuperarse de fallas de hardware, software o red.

6. RNF: Los datos de alquiler de autos deben ser respaldados regularmente y deben existir procedimientos para restaurarlos en caso de ser necesario.

7. RNF: El sistema debe ser fácil de usar para los usuarios, tanto para el personal de la empresa de alquiler de automóviles como para los clientes.


##### Diseñar Base de Datos

`CATEGORIA`

| Id |         Nombre          |           Descripcion         |  Tarifa Diaria   | 
|----|-------------------------|-------------------------------|------------------|
| 1  | Hyundai Accent 1.5      | Sedán Mecánico                |    $250.000      |
| 2  | Chevrolet Joy 1.4       | Sedán Mecánico                |    $250.000      |
| 3  | Renault Duster Oroch 4x4| Camioneta Mecánica de Platón  |    $550.000      |
| 4  | Renault Koleos 2.5      | Camioneta Automática Especial |    $570.000      |          


`AUTOMÓVIL`

| Id |  Gama |   Color   | Kilometraje |    Estado    | Categoria Id |
|----|-------|-----------|-------------|--------------|--------------|
|  1 |   F   |   Gris    |  Ilimitado  |  Disponible  |      1       |
|  2 |   F   |   Rojo    |  Ilimitado  |  Rentado     |      2       |
|  3 |   VP  |   Negro   |  Ilimitado  |  Rentado     |      3       |
|  4 |   LE  |   Gris    |  Ilimitado  |  Disponible  |      4       |


`PERSONA`

| Id |  Nombre Completo   |Tipo Identidad|Numero Identidad|Edad| WhatsApp | Correo Electronico  |
|----|--------------------|--------------|----------------|----|----------|---------------------|
| 1  |   Pedro Ramirez    |    C.C.      |  1075287006    | 25 |3112960604| Ped.R74@gmail.com   |
| 2  |   Maria Lopez      |    C.E.      |  263557897745  | 38 |3105810733| LopezM232@gmail.com |
| 3  |   Jose Sánchez     |    C.C.      |   107589456    | 30 |3204918274| j77san_55@gmail.com |
|    |                    |              |                |    |          |                     |


`AUTOPERSONA`

| Id |  Cliente  | Automóvil Id | Persona Id |
| 1  | Cliente 1 |       4      |     1      |
| 2  | Cliente 2 |       1      |     2      |
| 3  | Cliente 3 |       3      |     3      |


> Ver

*Script de la base de datos

DROP DATABASE IF EXISTS Alquiler Automóvil;

CREATE DATABASE Alquiler Automóvil;

USE Alquiler Automóvil;

CREATE table CATEGORIA(
    Id Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Nombre nvarchar (200) NOT NULL,
    Descripción nvarchar (200) NOT NULL,
    Tarifa_Diaria float NOT NULL,
);

CREATE table AUTOMÓVIL(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Nombre nvarchar (200) NOT NULL,
    Gama nvarchar (50) NOT NULL,
    Color nvarchar (50) NOT NULL,
    Kilometraje nvarchar (50) Not NULL,
    Estado nvarchar (50) NOT NULL,
     FOREING KEY (Categoria_Id) REFERENCES Categoria(Id)  
);

CREATE table PERSON(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Nombre_Completo nvarchar (250) NOT NULL,
    Id_Tipo nvarchaar (50) NOT NULL,
    Id_Numero Int NOT NULL,
    Edad Int NOT NULL,
    WhatsApp Int NOT NULL,
    Correo_Electronico nvarchar (100) NOT NULLL
);

 CREATE table AutosPersona(
    Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    Cliente VARCHAR(100) NOT NULL,
    Automóvil_Id INT NOT NULL,
    persona_Id INT NOT NULL,
    FOREING KEY (autos_Id) REFERENCES Autos(Id)
    FOREING KEY (persona_Id) REFERENCES Persona(Id)
 );

![Modelo relacional del ejercicio](bd/MR.png)

># Ver planificación 

