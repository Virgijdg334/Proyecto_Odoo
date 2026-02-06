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
```
### 3. Ejecución del Script
El script `importar.py` realiza las siguientes acciones de forma automática:

* **Lectura de datos:** Carga el archivo `listado.csv` utilizando la codificación `latin1` para procesar correctamente caracteres especiales.
* **Conexión a DB:** Establece comunicación con el servidor PostgreSQL (Base de datos: `postgres`).
* **Gestión de Tablas:** Ejecuta la sentencia `CREATE TABLE IF NOT EXISTS` para preparar la tabla `import_centros`.
* **Carga de registros:** Recorre el DataFrame de Pandas e inserta los datos fila por fila mediante el método `iloc`.
* **Persistencia:** Ejecuta un `commit()` final únicamente si no han ocurrido errores durante el proceso.

Para lanzarlo, ejecuta en la terminal:
```bash
python importar.py
```
### 📊 Verificación de Resultados
A continuación se adjunta la captura de pantalla que demuestra:

* **Éxito en la ejecución:** El mensaje de confirmación en la terminal de VS Code.
* **Persistencia en DB:** La consulta SQL en **pgAdmin** mostrando los datos cargados en la tabla `import_centros`.
* **Verificación de autoría:** La barra de tareas y el reloj del sistema visibles para validar la realización de la práctica.

<img width="1050" height="537" alt="Captura de pantalla 2026-02-06 123415" src="https://github.com/user-attachments/assets/05bf0a59-8a88-4a99-a938-c75d0a945828" />


<img width="1365" height="767" alt="Captura de pantalla 2026-02-06 123915" src="https://github.com/user-attachments/assets/45b37641-ad6a-4267-a2fd-b4e16e02cc1e" />


---

### 📂 Estructura del Proyecto
* **`importar.py`**: Código fuente del proceso ETL (Extracción, Transformación y Carga).
* **`listado.csv`**: Fuente de datos original con el listado de centros.
* **`README.md`**: Documentación detallada del ejercicio y guía de ejecución.
