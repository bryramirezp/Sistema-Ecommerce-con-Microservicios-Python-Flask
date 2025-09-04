# Sistema de Microservicios para una Joyería ("El Brillo")

Este proyecto es una implementación de un sistema de comercio electrónico para una joyería ficticia llamada "El Brillo", desarrollado como parte del primer parcial de la materia "Integración de Aplicaciones y Computación en la Nube". La principal característica del proyecto es su **arquitectura de microservicios**, que desacopla las responsabilidades del negocio en servicios independientes y escalables.

## Demostración Visual

### 🖥️ Interfaz Principal
<img src="https://github.com/bryramirezp/Sistema-Ecommerce-con-Microservicios-Python-Flask/blob/main/Verificaci%C3%B3n%20en%20la%20Base%20de%20Datos.png?raw=1" alt="Interfaz principal de la joyería" width="100%">

---

### 📄 Factura Generada
<img src="https://github.com/bryramirezp/Sistema-Ecommerce-con-Microservicios-Python-Flask/blob/main/Resultado%20Final%20-%20Factura%20Generada.png?raw=1" alt="Factura generada en la interfaz" width="100%">

---

### 🗄️ Verificación en Base de Datos
<img src="https://github.com/bryramirezp/Sistema-Ecommerce-con-Microservicios-Python-Flask/blob/main/Verificaci%C3%B3n%20en%20la%20Base%20de%20Datos.png?raw=1" alt="Consulta a la base de datos mostrando la última factura" width="100%">

## 🚀 Arquitectura

El sistema se compone de cuatro componentes principales que se ejecutan de forma independiente:

- **1. Servidor Web (Frontend):**
  - Es una **Single Page Application (SPA)** construida con HTML, CSS y JavaScript puro.
  - Se encarga de renderizar el catálogo de productos, gestionar el carrito de compras y orquestar las llamadas a los diferentes microservicios.
  - Detecta dinámicamente el *hostname* para construir las URLs de los microservicios, lo que facilita su configuración y despliegue.

- **2. Microservicio de Productos:**
  - **Tecnología:** Python + Flask.
  - **Responsabilidad:** Gestionar y exponer el catálogo de productos de la joyería.
  - **Endpoint:** `GET /api/products`
  - **Formato de Respuesta:** `XML`.

- **3. Microservicio de Pedidos:**
  - **Tecnología:** Python + Flask.
  - **Responsabilidad:** Procesar el carrito de compras, validar los datos, calcular totales y registrar el pedido en la base de datos.
  - **Endpoint:** `POST /api/pedidos`
  - **Formato de Entrada:** `JSON`.

- **4. Microservicio de Facturas:**
  - **Tecnología:** Python + Flask.
  - **Responsabilidad:** Generar una factura detallada a partir de un ID de pedido existente.
  - **Endpoint:** `POST /api/facturas`
  - **Formato de Respuesta:** `XML`. El frontend utiliza **XSLT** para transformar este XML en una vista HTML legible para el usuario.

## 🛠️ Stack Tecnológico

- **Frontend:** HTML5, CSS3, JavaScript (ES6+)
- **Backend (Microservicios):** Python 3, Flask
- **Base de Datos:** MariaDB
- **Arquitectura:** Microservicios, API REST
- **Formatos de Datos:** JSON, XML, XSLT

## ✨ Características Principales

- **Desacoplamiento de Servicios:** Cada lógica de negocio (productos, pedidos, facturas) opera de forma independiente, permitiendo un desarrollo y mantenimiento más sencillos.
- **Comunicación Asíncrona:** El frontend utiliza peticiones asíncronas (`fetch`) para interactuar con los microservicios sin recargar la página.
- **Manejo de Diferentes Formatos de Datos:** El sistema demuestra la capacidad de consumir y producir datos tanto en JSON como en XML, una habilidad clave en la integración de aplicaciones.
- **Configuración Dinámica:** El frontend está diseñado para adaptarse fácilmente a diferentes entornos (local, producción) gracias a su detección automática de URLs.
- **Persistencia de Datos:** Todos los pedidos y facturas se almacenan de forma segura en una base de datos MariaDB.

## ⚙️ Instalación y Ejecución

Para ejecutar este proyecto en un entorno local, sigue estos pasos:

### Prerrequisitos
- Python 3.8 o superior
- `pip` (manejador de paquetes de Python)
- Un servidor de base de datos MariaDB o MySQL en ejecución.

### 1. Clonar el Repositorio
```bash
git clone https://github.com/tu-usuario/tu-repositorio.git
cd tu-repositorio
