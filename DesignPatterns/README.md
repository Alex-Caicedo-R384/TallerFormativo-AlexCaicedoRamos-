# **Gesti�n de Veh�culos**



## **Requerimientos del Proyecto**

### **1. Implementar M�todos para Agregar Veh�culos**
- **Agregar veh�culos** (Mustang y Explorer) desde la p�gina principal de la aplicaci�n.
- Actualmente, el proyecto cuenta con un patr�n **Repositorio** para manejar las operaciones CRUD de los veh�culos. Sin embargo, el equipo de QA ha reportado que no est� funcionando como se espera, por lo que es necesario revisarlo y corregir cualquier posible error.

### **2. Pruebas sin Conexi�n a la Base de Datos**
- El esquema de la base de datos a�n no est� listo, por lo que el equipo de bases de datos no ha podido completar la integraci�n.
- Se debe realizar las pruebas funcionales utilizando un repositorio **en memoria**. Esto permitir� trabajar en la funcionalidad mientras se espera la disponibilidad de la base de datos real.

### **3. Agregar Propiedades por Defecto**
- El equipo de negocio ha solicitado que cada veh�culo tenga el **a�o actual** y **20 propiedades adicionales** como valores por defecto.
- Se implementar� un **patr�n de dise�o Builder** para agregar estas propiedades, lo que permitir� una f�cil escalabilidad y modificaci�n de las propiedades de los veh�culos en el futuro sin muchos cambios en el c�digo.

### **4. Implementar un Patr�n Factory Method**
- Para anticipar la necesidad de agregar nuevos modelos de veh�culos en el futuro, el **Arquitecto de Software** sugiri� implementar el patr�n **Factory Method**.
- Este patr�n se utilizar� para crear nuevos veh�culos, permitiendo agregar otros modelos como el **Escape** sin modificar la l�gica existente.

---

## **Implementaci�n**

### **1. Repositorio en Memoria:**
- Se cre� la clase `InMemoryVehicleRepository` que almacena temporalmente los veh�culos en una lista en memoria.
- Esto permite hacer pruebas sin depender de una base de datos real hasta que la base de datos est� disponible.

### **2. M�todos para Agregar Veh�culos:**
- Se implementaron los m�todos `AddMustang` y `AddExplorer` dentro del `HomeController`.
- Estos m�todos permiten agregar los veh�culos a la aplicaci�n mediante botones en la interfaz de usuario.

### **3. Patrones de Dise�o:**

- **Patr�n Builder:**
   - La clase `VehicleBuilder` fue implementada para agregar las propiedades por defecto a los veh�culos de manera flexible.
   - Esto asegura que cualquier cambio futuro en las propiedades de los veh�culos sea f�cil de manejar.

- **Patr�n Factory Method:**
   - La clase `VehicleFactory` fue creada para centralizar la l�gica de creaci�n de veh�culos, facilitando la adici�n de nuevos modelos sin afectar otras partes del sistema.
   - Esto tambi�n permite mantener el c�digo organizado y escalable para el futuro.

---

## **Tecnolog�as Utilizadas**

- **ASP.NET Core MVC:** Framework para el desarrollo de aplicaciones web basadas en el patr�n MVC.
- **C#:** Lenguaje principal utilizado para la implementaci�n de la aplicaci�n.
- **Bootstrap:** Framework CSS para mejorar la apariencia y experiencia de usuario de la interfaz web.
- **Patrones de Dise�o:**
   - **Factory Method**
   - **Builder**
   - **Repository**

---

## **Gu�a de Uso**

### **1. Agregar Veh�culos**
En la p�gina principal, encontrar�s dos botones para agregar veh�culos:
- **Agregar Mustang**: Agrega un veh�culo Mustang al sistema.
- **Agregar Explorer**: Agrega un veh�culo Explorer al sistema.

Estos botones a�aden los veh�culos al repositorio en memoria para su posterior gesti�n.

### **2. Gestionar Veh�culos**
Una vez que los veh�culos est�n en la lista, podr�s realizar las siguientes acciones:
- **Encender Motor**: Haz clic en "Encender Motor" para arrancar el motor de un veh�culo.
- **Apagar Motor**: Haz clic en "Apagar Motor" para apagar el motor de un veh�culo.
- **Llenar Tanque**: Haz clic en "Llenar Tanque" para agregar gasolina al veh�culo seleccionado.

### **3. Ver Lista de Veh�culos**
En la p�gina principal se mostrar� una tabla con los veh�culos disponibles. Los datos mostrados incluyen:
- **ID** del veh�culo
- **Tipo** de veh�culo (Mustang, Explorer, etc.)
- **Marca** del veh�culo
- **Modelo** del veh�culo
- **Color** del veh�culo
- **Nivel de Gasolina** (en litros)
- **Estado del Motor** (si est� encendido o apagado)

---

