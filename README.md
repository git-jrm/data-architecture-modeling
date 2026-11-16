# Arquitectura de datos y escalabilidad de bases de datos

Casos de estudio de escalabilidad, arquitectura de datos y modelado dimensional de bases de datos, aplicados a escenarios inspirados en empresas reales. Documentados en español.

## Contenido

| Documento | Casos | Temas principales |
| :--- | :--- | :--- |
| **[Bases de datos para alta escalabilidad](https://github.com/git-jrm/database-architecture/blob/main/db-scaling-sql-nosql.md)** | Fracttal, MOBI, PCFactory | SQL vs NoSQL, soluciones híbridas, DynamoDB, Cassandra, Well-Architected Framework |
| **[Arquitectura de datos y modelado dimensional](https://github.com/git-jrm/database-architecture/blob/main/data-architecture-modeling.md)** | InfoHealth, Mercato | Data Lake por capas, Data Warehouse, gobernanza (DAMA-DMBOK), calidad de datos, modelo estrella (Kimball) |

## Bases de datos para alta escalabilidad

- **Fracttal:** MySQL escalado verticalmente hasta su límite. Se propone una arquitectura híbrida que mantiene MySQL y suma DynamoDB para los registros operativos, con migración en tres fases.
- **MOBI:** SQL Server se degrada en horas peak por el límite de conexiones concurrentes. Se propone conservarlo para datos críticos y usar Cassandra para sesiones y streaming.
- **PCFactory:** latencia en peaks de pedidos de e-commerce. Diseño de tabla en DynamoDB con clave compuesta, índices secundarios y ejemplos de CRUD con AWS CLI.

## Arquitectura de datos y modelado dimensional

- **InfoHealth (salud):** fuentes de datos dispersas y duplicación sin trazabilidad erosionan la confianza en los reportes. Se propone una arquitectura por capas (Data Lake RAW, TRUSTED y CURATED, más Data Warehouse con data marts), gobernanza y un plan de calidad con controles por zona.
- **Mercato (retail):** las consultas analíticas contra la base transaccional ralentizan el sistema. Se propone un Data Warehouse con enfoque bottom-up de Kimball: esquema estrella para ventas (productos, clientes, sucursales, tiempo) y dimensiones de cambio lento (tipo 4).

## Enfoque

Cada caso parte de un diagnóstico del problema y justifica las decisiones de diseño. En los casos de bases de datos, la propuesta resuelve un cuello de botella específico sin descartar la infraestructura existente.
