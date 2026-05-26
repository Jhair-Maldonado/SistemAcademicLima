# 🎓 SistemAcademicLima (EduCore AI)

> **Entorno de desarrollo del proyecto académico para el curso Desarrollo Web Integrado (UTP).**
> 
> Representamos una arquitectura moderna, basada en tecnologías actuales tanto en Frontend, Backend y Base de Datos, diseñada para la optimización de procesos en instituciones educativas mediante la integración de Inteligencia Artificial.

---

## 🚀 Sobre el Proyecto

Las instituciones educativas actuales enfrentan una fragmentación crítica de datos. **SistemAcademicLima** es un ecosistema web integral que centraliza la gestión académica de primaria y secundaria bajo los estándares del Ministerio de Educación (MINEDU). 

El sistema rompe con los esquemas tradicionales al implementar una arquitectura omnicanal para el control de asistencia (Kioscos físicos y web) y al integrar motores predictivos de IA para el análisis de riesgo de deserción escolar, reduciendo la carga administrativa de los docentes de horas a minutos.

### 🎯 Características Principales (Módulos)

* **🛡️ Seguridad y Usuarios:** Gestión de roles estructurada bajo el patrón *Class Table Inheritance* (Administradores, Docentes, Alumnos y Apoderados).
* **📚 Currículo MINEDU:** Evaluación paramétrica basada en Áreas, Competencias y Capacidades, automatizando la generación de promedios oficiales.
* **💻 Aula Virtual:** Gestión de carga académica, horarios, publicación de material didáctico y recepción de entregables.
* **⏱️ Asistencia Omnicanal:** Trazabilidad de asistencia integrada con hardware físico (Kioscos de entrada) mediante validación de tokens/MAC, y marcación web.
* **🧠 Dirección e IA Predictiva:** Dashboard institucional y analítica impulsada por **Google Gemini**, capaz de generar alertas tempranas de bajo rendimiento e incidencias conductuales.

---

## 🛠️ Stack Tecnológico

El proyecto está construido utilizando herramientas de grado empresarial para garantizar escalabilidad, seguridad y alta concurrencia.

**Frontend:**
* React (Single Page Application)
* *Librerías:* Axios, React Router, TailwindCSS / Material-UI (o el framework CSS que decidan usar)

**Backend:**
* Java EE (JDK 17+)
* *Arquitectura:* MVC (Modelo-Vista-Controlador) y DAO (Data Access Object)
* *Servidor:* Apache Tomcat / GlassFish
* *APIs:* Servicios RESTful para comunicación con el cliente y hardware externo.

**Base de Datos:**
* MySQL 8.0+
* Diseño relacional normalizado en 3NF.

**Integraciones Externas:**
* Google Gemini API (Análisis predictivo de datos académicos)
* API RENIEC (Autocompletado de datos de registro)

---

## 📐 Arquitectura de Datos

La base de datos ha sido modelada para soportar las reglas de negocio del sector educativo peruano (como la capacidad máxima de alumnos por aula y la trazabilidad de evaluaciones). 

🔗 **[Ver Diagrama de Entidad-Relación (ERD) Completo](Coloca-Aqui-Tu-Enlace-De-Eraser-O-Dbdiagram)**

---

## ⚙️ Configuración y Despliegue Local

### Prerrequisitos
* Java Development Kit (JDK) instalado.
* MySQL Server corriendo localmente en el puerto `3306`.
* Node.js y npm (para el entorno Frontend).
* IDE recomendado: Eclipse IDE for Enterprise Java / IntelliJ IDEA y VS Code.

### Pasos de Instalación

1. **Clonar el repositorio:**
   ```bash
   git clone [https://github.com/TuUsuario/SistemAcademicLima.git](https://github.com/TuUsuario/SistemAcademicLima.git)
