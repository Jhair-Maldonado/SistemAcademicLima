# SistemAcademicLima (EduCore AI)

**Entorno de desarrollo del proyecto académico para el curso Desarrollo Web Integrado (UTP).**

Representamos una arquitectura moderna, basada en tecnologías actuales tanto en el Frontend, Backend y Base de Datos, diseñada para la optimización de procesos en instituciones educativas mediante la integración de Inteligencia Artificial.

---

## Sobre el Proyecto

Las instituciones educativas actuales enfrentan una fragmentación crítica de datos. **SistemAcademicLima** es un ecosistema web integral que centraliza la gestión académica de primaria y secundaria bajo los estrictos estándares del Ministerio de Educación (MINEDU). 

El sistema rompe con los esquemas tradicionales al implementar una arquitectura omnicanal para el control de asistencia (Kioscos físicos y portal web) y al integrar motores predictivos de Inteligencia Artificial para el análisis de riesgo de deserción escolar, reduciendo la carga administrativa institucional de horas a minutos.

### Módulos Principales

* **Seguridad y Usuarios:** Gestión de roles estructurada bajo el patrón *Class Table Inheritance* (Administradores, Docentes, Alumnos y Apoderados).
* **Currículo MINEDU:** Evaluación paramétrica basada en Áreas, Competencias y Capacidades, automatizando la generación de promedios oficiales.
* **Aula Virtual:** Gestión de carga académica, horarios, publicación de material didáctico y recepción de entregables.
* **Asistencia Omnicanal:** Trazabilidad de asistencia integrada con hardware físico (Kioscos de entrada) mediante validación de tokens/MAC, y marcación vía web.
* **Dirección e IA Predictiva:** Dashboard institucional y analítica impulsada por la API de Google Gemini, capaz de generar alertas tempranas de bajo rendimiento e incidencias conductuales.

---

## Stack Tecnológico

El proyecto está construido utilizando herramientas robustas para garantizar escalabilidad, seguridad y alta concurrencia.

**Frontend:**
* Angular (Framework principal para la Single Page Application)
* TypeScript, HTML5, CSS3/SASS
* RxJS (Programación reactiva) y Angular Material / Tailwind CSS para el diseño UI.

**Backend:**
* Java EE (JDK 17+)
* Arquitectura basada en los patrones MVC (Modelo-Vista-Controlador) y DAO (Data Access Object)
* Servidor de aplicaciones: Apache Tomcat
* APIs: Servicios RESTful (JAX-RS) para comunicación con el cliente y consumo de IA.

**Base de Datos:**
* MySQL 8.0+
* Diseño relacional normalizado hasta la Tercera Forma Normal (3NF).

**Integraciones Externas:**
* Google Gemini API (Análisis predictivo de datos académicos).
* API RENIEC (Autocompletado de datos para registro de usuarios).

---

## Arquitectura del Proyecto

El código fuente está dividido en dos grandes bloques que se comunican exclusivamente a través de servicios REST, asegurando un bajo acoplamiento.

### Estructura del Frontend (Angular)
El cliente web sigue una arquitectura modular basada en características (*Feature-driven architecture*).

```text
frontend/
├── src/
│   ├── app/
│   │   ├── core/                 # Servicios singleton, interceptores HTTP, guards de rutas
│   │   ├── features/             # Módulos principales de la aplicación
│   │   │   ├── admin/            # Dashboard de Dirección y gestión institucional
│   │   │   ├── attendance/       # Lógica de asistencia (Web y Kiosco)
│   │   │   ├── classroom/        # Aula virtual, tareas y notas MINEDU
│   │   │   └── auth/             # Componentes de login y recuperación
│   │   ├── shared/               # Componentes reutilizables (botones, modales, pipes)
│   │   ├── app-routing.module.ts # Enrutador principal
│   │   └── app.component.ts      # Componente raíz
│   ├── assets/                   # Imágenes, íconos y estilos globales
│   └── environments/             # Variables de entorno (Desarrollo/Producción)
├── angular.json                  # Configuración del workspace
└── package.json                  # Dependencias de npm
```

## Estructura del Backend (Java EE)

El servidor implementa un diseño por capas para separar la lógica de presentación (APIs), la lógica de negocio y el acceso a datos.

```text

backend/
├── src/
│   ├── main/
│   │   ├── java/com/educore/
│   │   │   ├── controllers/      # Servlets y Controladores REST (Endpoints)
│   │   │   ├── services/         # Lógica de negocio e integraciones (IA Gemini)
│   │   │   ├── dao/              # Clases Data Access Object para consultas SQL
│   │   │   ├── models/           # Entidades (Usuario, Alumno, Nota, etc.)
│   │   │   ├── utils/            # Utilidades (Conexión a BD, encriptación, JWT)
│   │   │   └── filters/          # Filtros de seguridad y CORS
│   │   └── webapp/
│   │       ├── WEB-INF/
│   │       │   └── web.xml       # Descriptor de despliegue del servidor web
│   │       └── META-INF/
│   │           └── context.xml   # Configuración del pool de conexiones a la BD
└── pom.xml                       # Gestión de dependencias de Maven (Librerías JSON, MySQL Driver)
```

## Configuración y Despliegue Local
## Prerrequisitos

   * Java Development Kit (JDK 17) instalado.

   * Node.js (v18+) y Angular CLI instalados.

   * MySQL Server ejecutándose en el puerto 3306.

## Pasos de Instalación

   1. Clonar el repositorio:
```bash ```
    git clone [https://github.com/TuUsuario/SistemAcademicLima.git](https://github.com/TuUsuario/SistemAcademicLima.git)

   2. Configuración de la Base de Datos:

       * Abre tu cliente SQL (MySQL Workbench).

       * Ejecuta el script database/schema.sql para construir la estructura relacional.

       * Ejecuta database/seed.sql para insertar los roles y usuarios de prueba.
    3. Despliegue del Backend:

       * Importa la carpeta backend en tu IDE (Eclipse / IntelliJ) como un proyecto Maven.

       * Configura tus credenciales locales de MySQL en el archivo utils/DatabaseConnection.java o context.xml.

       * Despliega el proyecto en Apache Tomcat. El servidor se expondrá por defecto en http://localhost:8080/SistemAcademicLima.
    4. Despliegue del Frontend:

       *  Abre una terminal y navega a la carpeta del cliente web.
    ```bash ```
    cd frontend
    npm install
    ng serve --open

       * La aplicación estará disponible en http://localhost:4200.

## Equipo de Desarrollo

## Proyecto de Ingeniería de Software desarrollado por estudiantes de la Universidad Tecnológica del Perú (UTP):

   1. Maldonado Quintana, Jhair Junior

   2. Pajuelo Cardenas, Joseph Jefferson

   3. Porras Palpa, Jair Alexander

## Curso: Desarrollo Web Integrado

## Docente: Mendoza Arce, Franz Bruce
