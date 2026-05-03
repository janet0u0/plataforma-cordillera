# Plataforma de Monitoreo Inteligente - Grupo Cordillera

## 📌 Descripción
Sistema de monitoreo organizacional basado en arquitectura de 
microservicios para el Grupo Cordillera. Centraliza datos de 
ventas, KPIs e indicadores en tiempo real.

## 👥 Autores
- Janet Huaylla Huayllas
- Bairo Pasten Codoceo

## 🎓 Asignatura
Desarrollo Fullstack III (DSY1106)
Profesor: Roberto Andres Moreno Perez

## 🏗️ Arquitectura
Frontend (React) → BFF (puerto 8084) → MS-Usuarios (8081)
→ MS-KPI      (8082)
→ MS-Datos    (8083)

## 📦 Repositorios
| Componente | URL | Puerto |
|---|---|---|
| Frontend | https://github.com/janet0u0/frontend-cordillera | 3000 |
| BFF | https://github.com/janet0u0/bff-cordillera | 8084 |
| MS-Usuarios | https://github.com/janet0u0/ms-usuarios | 8081 |
| MS-KPI | https://github.com/janet0u0/ms-kpi | 8082 |
| MS-Datos | https://github.com/janet0u0/ms-datos | 8083 |

## 🎯 Patrones implementados
- **Repository Pattern**: MS-Usuarios, MS-KPI, MS-Datos
- **Factory Method**: BFF (ReporteFactory)
- **Circuit Breaker**: BFF (MicroservicioClient)

## 🚀 Cómo ejecutar todo el sistema

### Paso 1 - Clonar todos los repositorios
```bash
git clone https://github.com/janet0u0/ms-usuarios.git
git clone https://github.com/janet0u0/ms-kpi.git
git clone https://github.com/janet0u0/ms-datos.git
git clone https://github.com/janet0u0/bff-cordillera.git
git clone https://github.com/janet0u0/frontend-cordillera.git
```

### Paso 2 - Levantar bases de datos
```bash
cd ms-usuarios/ms-usuarios && docker-compose up -d
cd ms-kpi/ms-kpi && docker-compose up -d
cd ms-datos/ms-datos && docker-compose up -d
```

### Paso 3 - Ejecutar microservicios
Abrir una terminal por cada uno:
```bash
cd ms-usuarios/ms-usuarios && mvn spring-boot:run
cd ms-kpi/ms-kpi && mvn spring-boot:run
cd ms-datos/ms-datos && mvn spring-boot:run
cd bff-cordillera/bff-cordillera && mvn spring-boot:run
cd frontend-cordillera && npm start
```

### Paso 4 - Acceder al sistema
- Frontend: http://localhost:3000
- BFF: http://localhost:8084/api/bff/dashboard?rol=EJECUTIVO

## ✅ Requisitos
- Java 17+
- Maven
- Docker Desktop
- Node.js 18+