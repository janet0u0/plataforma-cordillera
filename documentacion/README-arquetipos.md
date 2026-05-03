GUÍA DE ARQUETIPOS MAVEN
Plataforma de Monitoreo Inteligente - Grupo Cordillera
Autores: Janet Huaylla Huayllas - Bairo Pasten Codoceo

¿QUÉ ES UN ARQUETIPO MAVEN?
Un arquetipo Maven es una plantilla base que se usó para crear 
cada microservicio del proyecto. Se generó desde start.spring.io 
con las configuraciones necesarias para Spring Boot.

ARQUETIPO UTILIZADO
Todos los microservicios fueron creados con:
- Herramienta: https://start.spring.io
- Project: Maven
- Language: Java 17
- Spring Boot: 3.5.14
- Group: com.cordillera

ESTRUCTURA BASE DE CADA MICROSERVICIO
src/
├── main/java/com/cordillera/
│   ├── controller/   → Endpoints REST
│   ├── service/      → Lógica de negocio
│   ├── repository/   → Patrón Repository
│   ├── model/        → Entidades JPA
│   └── dto/          → Objetos de transferencia
└── test/java/        → Pruebas unitarias

CÓMO CREAR UN NUEVO MICROSERVICIO
1. Ir a https://start.spring.io
2. Configurar Project: Maven, Java: 17, Spring Boot: 3.5.14
3. Group: com.cordillera, Artifact: ms-nuevo
4. Agregar dependencias: Spring Web, JPA, MySQL, Lombok
5. Clic en GENERATE y extraer el ZIP
6. Crear docker-compose.yml con nuevo puerto MySQL
7. Configurar application.properties con nuevo puerto

MICROSERVICIOS DEL PROYECTO
MS-Usuarios  → Puerto 8081, MySQL puerto 3306
MS-KPI       → Puerto 8082, MySQL puerto 3307
MS-Datos     → Puerto 8083, MySQL puerto 3308
BFF          → Puerto 8084, sin base de datos

ARCHIVO pom.xml
El pom.xml es el archivo principal del arquetipo Maven.
Contiene las dependencias y configuraciones del proyecto.
Cada microservicio tiene su propio pom.xml.