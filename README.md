# Corte2_1075287060
# Control Automóvil. 

#### Necesidad:  
La idea es saber en un programa sobre 'el cliente' que necesitan 'alquiler' un automóvil. Que 'categoría' y quien fue el encargado de ese 'auto'



#### Análisis: Definición de requerimientos. 

1. RF1: El sistema debe permitir crear nuevos clientes, eliminar, actualizar información, esta debe ser completa (Id, Nombre Completo, Cedula o Pasaporte, Licencia de Conducir, Direccion, telefono, Correo Electronico) 
2. RF2:El sistema debe permitir buscar,  mostrar una lista de cliente por nombre, cédula de identidad o pasaporte, licencia de conducir y dirección.
4.RF3: El sistema debe mostrar una lista de vehículos con su información (marca, modelo, color, kilometraje, categoría, estado).
3. RF4: El sistema debe permitir crear nuevos vehículos, editar información de vehículos existente,  eliminar.
4.RF5: El sistema debe permitir seleccionar un cliente para un alquiler, seleccionar un vehículo para un alquiler,  registrar la fecha y hora de inicio del alquiler y fecha y hora de fin del alquiler.
5. RF6: El sistema debe mostrar una lista de alquileres activos con su información (cliente, vehículo, fecha y hora de inicio, fecha y hora de fin, costo total).


1. RNF1: 
2. RNF1: 
3. RNF1: 

#### Diseñar Base de Datos
Datos a tener en cuenta

| código | Nombre            | Cedula o Pasaporte| Licencia de Conducir |  Direccion   | Telefono | Email   |
|--------|-------------------|-------------------|----------------------|--------------|----------|---------|
|  4526  | Pedro Gonzalez    | 1075287060        |     A2 - B1          |     Cll 26a  |3105810733|  Pedro@ |  
|  7732  | Lorena Cruz       | 1075286328        |        B1            |     Cra 35a  |3112970604|  Lcruz@ |
|  2834  | Ramiro Montealegre| 1075349785        |     A2 - B1          |   Av La Toma |3204918274|  RamiM@ |
|  3349  | Juan Pedrasa      | 1075281567        |        A1            |     Cll 34a  |3143571823|   JP@   |

* De lo anterior, se puede resaltar lo siguiente, si bien es cierto, se puede ingresar los datos sin normalización, se sabe que es necesario para la optimización y traza de los datos. 

En este sentido, se procede a normarlizar de la siguiente manera. 

* La clasificación de los galpones, estos son individuales. 

`Cliente`
| id |código | Ubicación | Capacidad |Estado     |
|----|-------|-----------|-----------|-----------|
|  1 |101    |C-101      |2500       |True       |
|  2 |102    |C-102      |2400       |True       |
|  3 |112    |B-112      |600        |False      |
|  4 |112    |A-112      |1600       |False      |

* Se conoce que inicio de un cultivo, se requiere de la disponibilidad del galpon. Al Asignar un grupo de pollos al galpon, se debe `ocupar` el galpo  

`Automóvil`
| id    |          |            |          | 
|-------|----------|------------|----------|
|   1   |          |            |   4      |
|   2   |          |            |   3      |
|   3   |          |            |   3      |


> Ver
![Modelo relacional del ejercicio](bd/MR.png)

># Ver planificación 
 https://github.com/IBSanchezR/Corte2_1075287060.git