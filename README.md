# 🏫 Automatización de Datos en Odoo con Python (Proceso ETL)

Este proyecto consiste en el desarrollo de un script en **Python** diseñado para realizar un proceso de **ETL** (Extracción, Transformación y Carga). El objetivo es automatizar la migración de datos desde un archivo CSV externo hacia una base de datos **PostgreSQL** vinculada a una instancia de **Odoo** en Docker.

---

## 🛠️ Requisitos Técnicos

* **Lenguaje:** Python 3.10+
* **Infraestructura:** Docker Desktop (Contenedores de Odoo y DB activos).
* **Librerías Obligatorias:**
  * `pandas`: Para la manipulación y limpieza de datos.
  * `psycopg2-binary`: Para la conexión y ejecución de sentencias SQL en PostgreSQL.

---

## 🚀 Procedimiento de Configuración y Ejecución

### 1. Preparación del Entorno
Asegúrese de que el entorno Docker esté corriendo. El script utiliza las credenciales por defecto:
* **Host:** `localhost`
* **Puerto:** `5432`
* **Usuario/Password:** `odoo` / `odoo`

### 2. Instalación de Dependencias
Ejecute el siguiente comando en su terminal para instalar las librerías necesarias:
```bash
pip install pandas psycopg2-binary
3. Ejecución del Script
El script importar.py realiza las siguientes acciones de forma automática:

Lee el archivo listado.csv usando codificación latin1.

Conecta con la base de datos postgres.

Crea la tabla import_centros si no existe previamente.

Recorre el archivo e inserta los registros fila por fila.

Realiza un commit() final para asegurar la persistencia de los datos.

Para lanzarlo:

Bash
python importar.py
📊 Verificación de Resultados
A continuación se adjunta la captura de pantalla que demuestra:

El mensaje de éxito en la terminal de VS Code.

La consulta SQL en pgAdmin mostrando los datos cargados en la tabla import_centros.

La barra de tareas/reloj del sistema para verificar la autoría.

AQUÍ DEBES PEGAR TU CAPTURA DE PANTALLA

📂 Estructura del Proyecto
importar.py: Código fuente del proceso ETL.

listado.csv: Fuente de datos original.

README.md: Documentación del ejercicio.
