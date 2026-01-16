# Databricks Telco 📱

Un proyecto integral de gobernanza de datos para el sector de telecomunicaciones utilizando **Databricks Unity Catalog**, demostrando cómo gestionar, catalogar y gobernar datos de forma centralizada implementando la arquitectura **medallion** (Bronze → Silver → Gold) con catálogos unificados.

## 📋 Tabla de Contenidos

- [Descripción General](#descripción-general)
- [Características](#características)
- [Tecnologías](#tecnologías)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Requisitos Previos](#requisitos-previos)
- [Instalación y Configuración](#instalación-y-configuración)
- [Guía de Uso](#guía-de-uso)
- [Módulos Disponibles](#módulos-disponibles)
- [Catálogos y Esquemas](#catálogos-y-esquemas)
- [Datos de Telecomunicaciones](#datos-de-telecomunicaciones)
- [Flujo de Datos](#flujo-de-datos)
- [Mejores Prácticas](#mejores-prácticas)

## 🎯 Descripción General

**Databricks Telco** es un proyecto educativo y productivo que demuestra las capacidades avanzadas de **Unity Catalog** en Databricks para datos de telecomunicaciones. El proyecto implementa:

- ✅ **Gobernanza centralizada** de datos con Unity Catalog
- ✅ **Control de acceso granular** a nivel de objetos
- ✅ **Catálogos multi-workspace** compartidos
- ✅ **Lineage tracking** automático de datos
- ✅ **Arquitectura medallion** completa (Bronze-Silver-Gold)
- ✅ **Datos de ejemplo** del sector telecom (clientes, servicios, uso)

Perfecto para aprender Unity Catalog y aplicarlo a casos reales de telecomunicaciones.

## ✨ Características

### 🔐 Gobernanza de Datos Enterprise
- **Unity Catalog**: Catálogo centralizado y seguro
- **Control de acceso**: RBAC granular por tabla, columna, fila
- **Auditoría completa**: Rastreo de quién accede qué datos
- **Data lineage**: Visualización de orígenes y transformaciones
- **Compartir datos**: Metastore compartido entre workspaces
- **External Locations**: Integración con cloud storage

### 📊 Arquitectura Medallion
- **Bronze Catalog**: Datos raw sin procesar
- **Silver Catalog**: Datos limpios y validados
- **Gold Catalog**: Datos optimizados para análisis
- **Esquemas organizados** por dominio de negocio
- **Transacciones ACID** con Delta Lake
- **Versionado** automático de datos

### 📱 Dominio Telecom
- **Datos de clientes**: Información demográfica
- **Planes de servicio**: Catálogo de servicios
- **Uso de servicios**: Logs de consumo
- **Facturación**: Ingresos por cliente
- **Churn analysis**: Predicción de cancelaciones
- **Network data**: Información de redes

### 🛠️ Herramientas y Técnicas
- **Jupyter Notebooks**: Desarrollo interactivo
- **Python con PySpark**: Transformaciones distribuidas
- **SQL nativo**: Consultas de alto rendimiento
- **Delta Lake**: Transacciones y time travel
- **Databricks SQL**: Queries optimizadas
- **MLflow**: Gestión de modelos

### 🎓 Componentes Educativos
- **Unity Catalog Introduction**: Conceptos fundamentales
- **Mini-project**: Proyecto práctico completo
- **Ejemplos de código**: Casos de uso reales
- **Mejores prácticas**: Patrones probados
- **Documentación**: Explicaciones detalladas

## 🔧 Tecnologías

| Tecnología | Descripción | Propósito |
|-----------|-------------|----------|
| **Databricks** | Plataforma de analytics | Infraestructura principal |
| **Unity Catalog** | Gobernanza de datos | Catálogo centralizado |
| **Apache Spark (PySpark)** | Motor distribuido | Transformaciones ETL |
| **Delta Lake** | Formato transaccional | Almacenamiento fiable |
| **Databricks SQL** | SQL engine optimizado | Consultas analíticas |
| **Python 3.8+** | Lenguaje de programación | Notebooks y scripts |
| **Jupyter Notebooks** | Desarrollo interactivo | Análisis y transformaciones |
| **SQL** | Lenguaje de consultas | DDL/DML operations |
| **Azure/AWS Storage** | Cloud storage | External locations |
| **MLflow** | ML tracking | Modelos y experimentos |

## 📁 Estructura del Proyecto

```yaml
databricks-course/
│
├── 🎓 unity-catalog-introduction/ # Módulo Educativo
│ ├── 01.query_tables_with_unity_catalog.ipynb
│ │ └── Aprende a usar Unity Catalog
│ │ - Explorar catálogos
│ │ - Consultar tablas
│ │ - Permisos de acceso
│ │
│ └── 02.access_external_locations.ipynb
│ └── Trabajar con ubicaciones externas
│ - Conectar cloud storage
│ - Gestionar datos externos
│ - Controladores externas
│
├── 🚀 unity-catalog-mini-project/ # Proyecto Práctico Completo
│ ├── 01.create_external_locations.ipynb
│ │ └── Configurar almacenamiento externo
│ │ - Crear External Locations
│ │ - Configurar credenciales
│ │ - Validar conectividad
│ │
│ ├── 02.create_catalog_schemas.ipynb
│ │ └── Crear estructura de catálogos
│ │ - Catálogo: telco_data
│ │ - Esquema: bronze
│ │ - Esquema: silver
│ │ - Esquema: gold
│ │ - Permisos y owners
│ │
│ ├── 03.create_bronze_tables.ipynb
│ │ └── Crear capa Bronze (datos crudos)
│ │ - customers (clientes)
│ │ - services (servicios)
│ │ - usage (uso de servicios)
│ │ - billing (facturación)
│ │ - network_data (datos de red)
│ │
│ ├── 04.create_silver_tables.ipynb
│ │ └── Crear capa Silver (datos limpios)
│ │ - Transformación de datos
│ │ - Validaciones
│ │ - Enriquecimiento
│ │ - Deduplicación
│ │
│ └── 05.create_gold_tables.ipynb
│ └── Crear capa Gold (datos análisis)
│ - Agregaciones
│ - Métricas clave (KPIs)
│ - Tablas para BI
│ - Optimización
│
└── 📄 README.md # Este archivo
```

## 📋 Requisitos Previos

### Databricks Setup
- **Workspace de Databricks** activo (Community o Premium)
- **Privilegios de Admin** en el workspace
- **Unity Catalog** habilitado en la cuenta Databricks
- **Metastore** configurado
- **Compute cluster** con runtime 11.3 LTS o superior

### Cloud Storage
- **Azure Blob Storage** OR **AWS S3** (según tu cloud)
- **Contenedor/bucket** para External Locations
- **Credenciales** configuradas (connection string o IAM role)

### Acceso y Permisos
- Crear catálogos y esquemas
- Crear tablas
- Gestionar external locations
- Asignar permisos a usuarios

### Herramientas Locales (opcional)
- **Databricks CLI** instalado
- **Visual Studio Code** con extensión Databricks
- **Git** para versionado
- **Python 3.8+** para desarrollo local

## 🚀 Instalación y Configuración

### 1. Clonar el Repositorio

```bash
git clone https://github.com/jordytiradotorres/Databricks-Telco.git
cd Databricks-Telco
```

### 2. Acceder a Databricks Workspace

# Opción 1: Desde Azure Portal / AWS Console
# Ve a tu Databricks workspace y abre "Workspace"

# Opción 2: Usar Databricks CLI
databricks configure --token
# Ingresa: host y tu PAT token

### 3. Crear Metastore (Si es primera vez)

# En un notebook Databricks, ejecuta:
CREATE METASTORE telco_metastore
  LOCATION 's3://my-bucket/metastore' -- o Azure equivalent

### 4. Clonar/Importar Notebooks
Opción A: Importar desde GitHub

1. En Databricks UI: Workspace → Import
2. Selecciona "URL"
3. Pega: https://github.com/jordytiradotorres/Databricks-Telco
4. Selecciona dónde importar

Opción B: Usar Databricks CLI

databricks workspace import_directory \
  ./databricks-course \
  /Users/your-username/telco-project

### 5. Configurar External Locations
En notebook: 01.create_external_locations.ipynb

# Para Azure
CREATE EXTERNAL LOCATION telco_external_location
URL 'abfss://telco-data@mystorageaccount.dfs.core.windows.net/'
WITH (CREDENTIAL `my_credential`)

# Para AWS
CREATE EXTERNAL LOCATION telco_external_location
URL 's3://my-telco-bucket/'
WITH (CREDENTIAL `my_aws_credential`)

### 6. Ejecutar Módulo de Introducción

1. Abre: unity-catalog-introduction/01.query_tables_with_unity_catalog.ipynb
2. Sigue las instrucciones paso a paso
3. Ejecuta celdas para aprender conceptos
4. Experimenta con permisos

### 7. Ejecutar Mini-proyecto
Ejecuta en orden:

1. 01.create_external_locations.ipynb
2. 02.create_catalog_schemas.ipynb
3. 03.create_bronze_tables.ipynb
4. 04.create_silver_tables.ipynb
5. 05.create_gold_tables.ipynb

### 🎮 Guía de Uso
Flujo de Ejecución del Mini-proyecto

```yaml
Paso 1: External Locations
  └─ Crear conexión a cloud storage
  
Paso 2: Catálogos y Esquemas
  └─ Crear estructura: telco_data
     ├─ bronze (datos crudos)
     ├─ silver (datos limpios)
     └─ gold (datos análisis)

Paso 3: Bronze Layer
  └─ Cargar datos raw de clientes, servicios, uso, etc.

Paso 4: Silver Layer
  └─ Transformar, limpiar, validar datos

Paso 5: Gold Layer
  └─ Crear tablas optimizadas para análisis
```

### 📚 Módulos Disponibles
🎓 Unity Catalog Introduction

01.query_tables_with_unity_catalog.ipynb
Objetivos:

- Entender estructura de Unity Catalog
- Explorar catálogos y esquemas
- Consultar tablas
- Gestionar permisos
- Ver data lineage

Tópicos:

- 3-level namespace (catalog.schema.table)
- Explorando metadatos
- Permisos en objetos
- Cross-workspace access

02.access_external_locations.ipynb
Objetivos:

- Conectar cloud storage
- Gestionar credenciales
- Crear external locations
- Leer/escribir datos externos

Tópicos:

- Configurar credenciales
- Crear external locations
- Volumes vs Tables
- Auditoría de acceso

### 🚀 Unity Catalog Mini-project
Proyecto completo de gobernanza para sector telecomunicaciones.

01.create_external_locations.ipynb
Crea:

- External Location en cloud storage
- Credenciales securizadas
- Validación de conectividad

Aprenderás:

- Integración cloud
- Gestión de secretos
- Validación de acceso

02.create_catalog_schemas.ipynb
Crea:

- Catálogo: telco_data
- 3 Esquemas: bronze, silver, gold
- Asignación de propietarios
- Permisos iniciales

### Esquema:

```text
Catálogo: telco_data
├── Schema: bronze (datos raw)
├── Schema: silver (datos limpios)
└── Schema: gold (datos para BI)
```

03.create_bronze_tables.ipynb
Crea tablas raw:

- customers: Información de clientes (ID, nombre, email, etc.)
- services: Catálogo de servicios (planes, tipos)
- usage: Registros de uso de servicios
- billing: Facturas y pagos
- network_data: Información de red y conectividad

Características:

- Datos sin procesar
- Estructura original preservada
- Full load initial
- Timestamp de carga

04.create_silver_tables.ipynb
Crea tablas limpias:

- customers_clean: Datos validados
- services_clean: Servicios normalizados
- usage_clean: Uso sin duplicados
- billing_clean: Facturas consolidadas

Transformaciones:

- Eliminación de nulos
- Normalización de formatos
- Deduplicación
- Enriquecimiento con datos master
- Validaciones de integridad

05.create_gold_tables.ipynb
Crea tablas analíticas:

- customer_metrics: KPIs por cliente
- service_adoption: Adopción de servicios
- revenue_analysis: Análisis de ingresos
- churn_indicators: Indicadores de cancelación
- network_performance: Métricas de red

Optimizaciones:

- Agregaciones precomputadas
- Índices optimizados
- Compresión Delta
- Particionamiento estratégico

### 📊 Datos de Telecomunicaciones
Dominio de Datos

```yaml
Clientes (Customers)
├── Datos demográficos
├── Información de contacto
├── Fecha de registro
└── Plan activo

Servicios (Services)
├── Tipos de servicios
│  ├─ Internet móvil
│  ├─ Internet fijo
│  ├─ Telefonía
│  └─ TV por cable
├── Planes disponibles
├── Precios
└── Características

Uso (Usage)
├── Datos consumidos (GB)
├── Minutos de llamadas
├── SMS enviados
├── Período de facturación
└── Timestamp

Facturación (Billing)
├── Monto cobrado
├── Fecha de pago
├── Método de pago
├── Estado de cuenta
└── Descuentos aplicados

Red (Network)
├── Cobertura
├── Velocidad
├── Disponibilidad
├── Latencia
└── Calidad de servicio
```

- Casos de Uso Analíticos
1. Análisis de Churn

Identificar clientes en riesgo
Patrones de cancelación
Retención por segmento

2. Revenue Analytics

ARPU (ingresos promedio por usuario)
LTV (lifetime value)
Oportunidades de upsell/cross-sell

3. Network Performance

Calidad de servicio
Optimización de infraestructura
Planificación de capacidad

4. Customer Segmentation

Segmentación por valor
Perfiles de comportamiento
Personalización de ofertas

### 📈 Flujo de Datos

```yaml
External Cloud Storage (Raw Data)
           ↓
┌─────────────────────────────┐
│   BRONZE Layer (telco_data.bronze)
│   - customers
│   - services
│   - usage
│   - billing
│   - network_data
└─────────────────────────────┘
           ↓
    [Data Transformation]
    (Limpieza, Validación)
           ↓
┌─────────────────────────────┐
│   SILVER Layer (telco_data.silver)
│   - customers_clean
│   - services_clean
│   - usage_clean
│   - billing_clean
└─────────────────────────────┘
           ↓
    [Aggregations & Analysis]
    (KPIs, Métricas)
           ↓
┌─────────────────────────────┐
│   GOLD Layer (telco_data.gold)
│   - customer_metrics
│   - service_adoption
│   - revenue_analysis
│   - churn_indicators
│   - network_performance
└─────────────────────────────┘
           ↓
┌─────────────────────────────┐
│   BI & Reporting
│   - Dashboards
│   - Data Apps
│   - SQL Queries
│   - ML Models
└─────────────────────────────┘
```

# 🔐 Mejores Prácticas

## 🏛️ Gobernanza de Datos
✅ **Usar 3-level namespace** (catalog.schema.table)  
✅ **Asignar propietarios claros** a cada objeto  
✅ **Implementar RBAC granular**  
✅ **Auditar acceso regularmente**  
✅ **Documentar lineage de datos**

## 🔒 Seguridad
✅ **Almacenar credenciales** en secrets  
✅ **Usar service principals** para automatización  
✅ **Implementar column-level security**  
✅ **Encriptar datos** en tránsito y reposo  
✅ **Monitorear acceso** con audit logs

## ⚡ Performance
✅ **Particionar tablas grandes**  
✅ **Usar índices** en columnas frecuentes  
✅ **Optimizar tamaño** de ficheros Delta  
✅ **Usar caching** apropiadamente  
✅ **Monitorear query performance**

## 🛠️ Mantenibilidad
✅ **Usar convención de nombres** consistente  
✅ **Documentar esquemas** y transformaciones  
✅ **Versionear código** y notebooks  
✅ **Testear transformaciones**  
✅ **Automatizar pipelines**
