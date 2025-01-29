# Proyecto de Gestión de Vehículos

## Descripción

Este proyecto es una aplicación web que permite gestionar vehículos mediante el uso de patrones de diseño en C#. Utilizando **ASP.NET Core MVC** y **Bootstrap**, los usuarios pueden agregar vehículos, ver su información y controlar el estado del motor y el nivel de gasolina.

## Requerimientos del Proyecto

El proyecto cuenta con los siguientes requerimientos funcionales:

### 1. Implementar métodos para agregar vehículos
- Agregar vehículos (**Mustang** y **Explorer**) desde la página principal (Home Page).
- El proyecto ya cuenta con un patrón **Repositorio** para manejar las operaciones CRUD de automóviles. Sin embargo, el equipo de QA ha reportado que no funciona como se espera. Es necesario revisarlo y corregirlo.

### 2. Probar funcionalidad sin conexión a la base de datos
- El equipo de bases de datos indicó que el esquema de la base de datos aún no está listo.
- Es necesario probar las funcionalidades utilizando un repositorio **en memoria** como solución temporal, para luego conectar con la base de datos una vez esté disponible.

### 3. Agregar propiedades por defecto
- El equipo de negocio solicitó agregar el año actual y **20 propiedades más** como valores por defecto en los vehículos.
- Implementar un patrón de diseño para agregar propiedades por defecto (por ejemplo, **Builder**) de manera que los cambios futuros sean mínimos.

### 4. Implementar un patrón Factory Method
- El Arquitecto de Software sugirió implementar el patrón **Factory Method** para crear nuevos modelos de vehículos, anticipando que se agregarán más modelos en el futuro.

---

## Implementación

El proyecto utiliza patrones de diseño para cumplir con los requerimientos:

1. **Repositorio en memoria:**
   - Se creó el repositorio `InMemoryVehicleRepository` para almacenar los vehículos temporalmente sin necesidad de una base de datos.

2. **Métodos para agregar vehículos:**
   - Se implementaron los métodos `AddMustang` y `AddExplorer` en el `HomeController` para permitir agregar vehículos desde la interfaz de usuario.

3. **Patrón Builder:**
   - Se diseñó la clase `VehicleBuilder` para agregar propiedades por defecto a los vehículos. Esto permite una fácil extensibilidad para futuros cambios.

4. **Patrón Factory Method:**
   - Se creó la clase `VehicleFactory` para centralizar la creación de nuevos modelos de vehículos, facilitando la adición de nuevas variantes como el modelo **Escape**.

---

## Tecnologías Utilizadas

- **ASP.NET Core MVC:** Para el desarrollo de la aplicación web.
- **C#:** Lenguaje principal para la implementación del proyecto.
- **Bootstrap:** Framework CSS utilizado para mejorar la interfaz de usuario.
- **Patrones de Diseño:**
  - Factory Method
  - Builder
  - Repository

---

## Guía de Uso

### 1. Agregar vehículos
Desde la página principal, haz clic en los botones:
- **Agregar Mustang**
- **Agregar Explorer**

Esto agregará los vehículos seleccionados al repositorio en memoria.

### 2. Gestionar vehículos
- **Encender motor:** Haz clic en "Encender Motor 🚀" para arrancar el motor de un vehículo.
- **Apagar motor:** Haz clic en "Apagar Motor 🛑" para apagar el motor.
- **Llenar tanque:** Haz clic en "Llenar Tanque ⛽" para añadir gasolina.

### 3. Ver lista de vehículos
En la tabla de la página principal podrás ver los siguientes datos:
- Identificador (ID)
- Tipo de vehículo
- Marca
- Modelo
- Color
- Nivel de gasolina
- Estado del motor (Encendido o Apagado)

---

## Autor

Este proyecto fue desarrollado por **Alex Caicedo Ramos**. Puedes contactarlo a través de su correo electrónico: chevyagcr@gmail.com.

Alex usó el repositorio de [https://github.com/RobertoArmas/Udla-Workshop-Design-Patterns.git](https://github.com/RobertoArmas/Udla-Workshop-Design-Patterns.git) para completar el taller formativo con las siguientes instrucciones:

### Design Patterns

Pepito es un Ingeniero de Software Junior en **Codificando Con Patrones Cía. Ltda.** Se le ha encargado la tarea de completar los requerimientos funcionales del aplicativo de automóviles al que la empresa da soporte.

Los requisitos son los siguientes:

- Implementar los métodos de agregar vehículos (add Mustang y add Explorer) en el Home Page. El programador anterior implementó un patrón repositorio que contiene los métodos CRUD para el repositorio de automóviles; sin embargo, el equipo de QA ha reportado que no funciona como se espera.

- El equipo de base de datos ha comentado que el esquema de la base de datos no está listo. Por lo que se necesita buscar una forma de probar la funcionalidad sin tener que guardar en la base de datos, de tal forma que después se implemente la funcionalidad de base de datos cuando esté lista.

- El equipo de negocio ha solicitado agregar el año actual, y 20 propiedades más por defecto que se solicitarán en el siguiente sprint. Estas propiedades afectan a vehículo. Implementa un patrón de diseño para agregar propiedades por defecto, y como lo diseñarías para minimizar los cambios para el siguiente sprint.

- Se planea agregar un nuevo modelo. El Arquitecto de Software prevee que la unidad de negocio, planeará la introducción de más modelos por lo cual sugiere la implementación de un Factory Method.
  - Color: Red
  - Marca: Ford
  - Modelo: Escape
