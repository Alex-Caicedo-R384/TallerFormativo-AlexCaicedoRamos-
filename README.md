# **Gestión de Vehículos**



## **Requerimientos del Proyecto**

### **1. Implementar Métodos para Agregar Vehículos**
- **Agregar vehículos** (Mustang y Explorer) desde la página principal de la aplicación.
- Actualmente, el proyecto cuenta con un patrón **Repositorio** para manejar las operaciones CRUD de los vehículos. Sin embargo, el equipo de QA ha reportado que no está funcionando como se espera, por lo que es necesario revisarlo y corregir cualquier posible error.

### **2. Pruebas sin Conexión a la Base de Datos**
- El esquema de la base de datos aún no está listo, por lo que el equipo de bases de datos no ha podido completar la integración.
- Se debe realizar las pruebas funcionales utilizando un repositorio **en memoria**. Esto permitirá trabajar en la funcionalidad mientras se espera la disponibilidad de la base de datos real.

### **3. Agregar Propiedades por Defecto**
- El equipo de negocio ha solicitado que cada vehículo tenga el **año actual** y **20 propiedades adicionales** como valores por defecto.
- Se implementará un **patrón de diseño Builder** para agregar estas propiedades, lo que permitirá una fácil escalabilidad y modificación de las propiedades de los vehículos en el futuro sin muchos cambios en el código.

### **4. Implementar un Patrón Factory Method**
- Para anticipar la necesidad de agregar nuevos modelos de vehículos en el futuro, el **Arquitecto de Software** sugirió implementar el patrón **Factory Method**.
- Este patrón se utilizará para crear nuevos vehículos, permitiendo agregar otros modelos como el **Escape** sin modificar la lógica existente.

---

## **Implementación**

### **1. Repositorio en Memoria:**
- Se creó la clase `InMemoryVehicleRepository` que almacena temporalmente los vehículos en una lista en memoria.
- Esto permite hacer pruebas sin depender de una base de datos real hasta que la base de datos esté disponible.

### **2. Métodos para Agregar Vehículos:**
- Se implementaron los métodos `AddMustang` y `AddExplorer` dentro del `HomeController`.
- Estos métodos permiten agregar los vehículos a la aplicación mediante botones en la interfaz de usuario.

### **3. Patrones de Diseño:**

- **Patrón Builder:**
   - La clase `VehicleBuilder` fue implementada para agregar las propiedades por defecto a los vehículos de manera flexible.
   - Esto asegura que cualquier cambio futuro en las propiedades de los vehículos sea fácil de manejar.

- **Patrón Factory Method:**
   - La clase `VehicleFactory` fue creada para centralizar la lógica de creación de vehículos, facilitando la adición de nuevos modelos sin afectar otras partes del sistema.
   - Esto también permite mantener el código organizado y escalable para el futuro.

---

## **Tecnologías Utilizadas**

- **ASP.NET Core MVC:** Framework para el desarrollo de aplicaciones web basadas en el patrón MVC.
- **C#:** Lenguaje principal utilizado para la implementación de la aplicación.
- **Bootstrap:** Framework CSS para mejorar la apariencia y experiencia de usuario de la interfaz web.
- **Patrones de Diseño:**
   - **Factory Method**
   - **Builder**
   - **Repository**

---

## **Guía de Uso**

### **1. Agregar Vehículos**
En la página principal, encontrarás dos botones para agregar vehículos:
- **Agregar Mustang**: Agrega un vehículo Mustang al sistema.
- **Agregar Explorer**: Agrega un vehículo Explorer al sistema.

Estos botones añaden los vehículos al repositorio en memoria para su posterior gestión.

### **2. Gestionar Vehículos**
Una vez que los vehículos estén en la lista, podrás realizar las siguientes acciones:
- **Encender Motor**: Haz clic en "Encender Motor" para arrancar el motor de un vehículo.
- **Apagar Motor**: Haz clic en "Apagar Motor" para apagar el motor de un vehículo.
- **Llenar Tanque**: Haz clic en "Llenar Tanque" para agregar gasolina al vehículo seleccionado.

### **3. Ver Lista de Vehículos**
En la página principal se mostrará una tabla con los vehículos disponibles. Los datos mostrados incluyen:
- **ID** del vehículo
- **Tipo** de vehículo (Mustang, Explorer, etc.)
- **Marca** del vehículo
- **Modelo** del vehículo
- **Color** del vehículo
- **Nivel de Gasolina** (en litros)
- **Estado del Motor** (si está encendido o apagado)

---

