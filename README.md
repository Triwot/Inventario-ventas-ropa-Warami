# 🛍️ Tienda Warani - POS & Gestión de Inventario Serverless

Un sistema web de Punto de Venta (POS) y control de inventario diseñado específicamente para digitalizar y optimizar la gestión comercial de una tienda de ropa. Este proyecto transforma operaciones manuales en un flujo digital automatizado, permitiendo monitorear métricas financieras en tiempo real y asegurar la rentabilidad del negocio.

## 🏗️ Arquitectura y Decisiones Técnicas

Este proyecto fue concebido bajo un enfoque de **cero costos de infraestructura (Zero-Cost Serverless)**, ideal para micro y pequeñas empresas que requieren alta disponibilidad sin incurrir en pagos de servidores SQL, hostings tradicionales o licencias de software.

### ¿Por qué un único archivo `index.html`?
El frontend está construido como una **Single Page Application (SPA) ultraligera** contenida enteramente en un solo archivo `index.html` (que integra HTML5, CSS3 y Vanilla JavaScript). 
* **Rendimiento y Simplicidad:** Al no depender de frameworks pesados (como React o Angular) ni empaquetadores (Webpack/Vite), la carga inicial es instantánea, incluso en dispositivos móviles de gama baja o conexiones inestables.
* **Despliegue Inmediato:** Permite un alojamiento directo y gratuito en plataformas como Netlify, donde cualquier actualización se refleja en segundos sin procesos complejos de build.

### ¿Por qué utilizar Google Sheets como Base de Datos?
En lugar de una base de datos relacional tradicional (como MySQL o PostgreSQL), el sistema utiliza un archivo de **Google Sheets** estructurado con tablas relacionales (`Inventario`, `Ventas`, `Compras`, `Usuarios`).
* **Backend API RESTful:** Mediante **Google Apps Script**, la hoja de cálculo se transforma en una API que procesa peticiones `GET` y `POST` (con endpoints para login, registro de ventas, ingresos y eliminación de registros).
* **Transparencia para el Cliente:** El propietario del negocio tiene acceso directo a los datos crudos en un formato (Excel/Sheets) que ya conoce y domina, facilitando auditorías manuales, copias de seguridad inmediatas y exportaciones contables sin requerir conocimientos en bases de datos.

## ✨ Características Principales

* 🔐 **Módulo de Autenticación (Login):** Barrera de seguridad para proteger las rutas del sistema. Incluye funcionalidad "Recuérdame" utilizando `localStorage` y `sessionStorage` para mantener la sesión activa.
* 👤 **Trazabilidad de Vendedores:** El sistema detecta qué usuario inició sesión y firma silenciosamente cada transacción de venta, permitiendo auditar el rendimiento y los movimientos de cada empleado en caja.
* 📈 **Cálculo de Costo Promedio Ponderado:** Al registrar el ingreso de nueva mercadería a precios fluctuantes, el algoritmo del backend recalcula automáticamente el costo unitario promedio, protegiendo el margen de ganancia real frente a la inflación.
* 🛒 **Punto de Venta (POS) Dinámico:** Selección rápida de prendas, edición de precios para descuentos instantáneos y cálculo automático de totales y ganancias netas.
* 📊 **Dashboard Analítico:** Panel de control con métricas en vivo (Ingresos, Ganancia, Valor en Bodega), historial de ventas y un módulo completo de inventario con opción de eliminación de registros.
* 🎨 **Diseño Soft UI (Glassmorphism):** Interfaz moderna, responsiva y minimalista basada en una paleta de colores morados, optimizada para la experiencia de usuario (UX) tanto en escritorio como en móviles.

## 🛠️ Stack Tecnológico

**Frontend:**
* HTML5 (Semántico)
* CSS3 (Flexbox, CSS Grid, Glassmorphism)
* JavaScript Vanilla (ES6+, Fetch API, DOM Manipulation)
* SweetAlert2 (Para modales y alertas interactivas)

**Backend & Base de Datos:**
* Google Apps Script (Lógica de servidor y API)
* Google Sheets (Persistencia de datos)

**Hosting:**
* Netlify (Despliegue continuo y alojamiento frontend)
  
🌐 **Demo en Vivo:** [Visitar Tienda Warani](https://tu-enlace-de-warani.netlify.app)
*(Nota: Inicia sesión con tus credenciales de administrador para ver el dashboard).*

## 🚀 Instalación y Uso Local

1. Clona este repositorio:
   ```bash
   git clone [https://github.com/triwot/tienda-warani.git](https://github.com/triwot/tienda-warani.git)
