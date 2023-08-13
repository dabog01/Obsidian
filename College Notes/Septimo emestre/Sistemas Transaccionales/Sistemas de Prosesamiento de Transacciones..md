	Conceptos
	1. Transacción: "Es un intercambio entre dos partes que se registra y se guarda en un un sistema de equipos de cómputo" -Jamrich (2008)

**Sistemas** utilizados en empresas el cual **recopila datos de transacciones/intercambios**  almacenados en la base de datos con el fin de **generar reportes** u otras informaciones del negocio y asi controlar las actividades del negocio

## Propiedades

* Automatizan tareas operativas en una organización 
* Dirigidas especialmente al area de ventas 
* Suelen ser los primeros sistemas implementados en una organixacion 
* Calculos y procesos simples
* Usualmente cargan grandes bases de datos
* Beneficios rapidamente visibles
* Almacenar grandes volumenes de datos, no analizarlos
## Caracterisiticas

#### ==Test ACID==

Acciones para garantizar que el trabajo de usuario no interfiera con el otro
##### **Propiedades**

1. **Atomicidad:** La transaccion se tiene que ejecutar totalmente o no ejecutarse
2. **Coherencia:** La transaccion debe ser valida
3. **Aislamiento:** La transaccion se debe terminar completamente para ser visible
4. **Durabilidad:** La transaccion almacenada no debe perderse por fallas subsecuentes
#### ==**Rapidez**==

La respuesta no debe ser mayor a un par de segundos
#### ==**Fiabilidad**==

Debe ser altamente fiable
#### ==**Inflexibilidad**==

No se acepta informacion distinta a la implantada
## Tipos

#### **- Sistema de ventas de marketing**

Administracion de ventas, investigacion de mercados, productos nuevos, sistemas de comisiones de venta, fijacion de precios
#### **- Sistemas de manufactura y produccion**

Programacion, compras, sistemas de ingenieria , control de calidad, control de maquinaria
#### **- Sistemas de finanzas y contabilidad**

Presupuestos, facturacion, contabilidad de costos, cuentas por cobrar
#### **- Sistemas de recursos Humanos**

Registro, nomina, expedientes




## Two Phase Commit - Distributed Transactions 

Recordemos los requisitos necesarios para que se haga una transaccion ***(ACID)***

Estamos hablando de que este tipo de bloqueo principalmente asegura la **Atomicidad** y **Aislamiento** en la transaccion

When data needs to be atomically stored on multiple cluster nodes, Cluster nodes cannot make the data accessible to clients before the decision of other cluster nodes is known. Each node needs to know if other nodes successfully stored the data or they failed.

The essence of two phase commit, unsurprisingly, is that it carries out an update in two phases:

- the first, prepare, asks each node if it's able to promise to carry out the update
- the second, commit, actually carries it out.

![[Two Phase Commit.png]]
### But There is a Few Problems

* Coordinator goes down?
No transactions can proceed, receiving nodes hold locks and can't touch rows
* Receiver goes down?
Transaction can't commit, coordinator needs send it messages until it comes back up
### *Basic* Block Types

#### Shared Lock
Lectura de datos
#### Exclusive Lock
Modificaciones de datos (INSERT / DELETE / UPDATE)

