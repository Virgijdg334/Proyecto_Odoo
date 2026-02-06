Automatización de Datos en Odoo con Python (Proceso ETL)
Este proyecto consiste en el desarrollo de un script en Python diseñado para realizar un proceso de ETL (Extracción, Transformación y Carga). El objetivo es automatizar la migración de datos desde un archivo CSV externo (listado.csv) hacia una base de datos PostgreSQL que sustenta una instancia de Odoo corriendo en contenedores Docker.

🛠️ Requisitos Técnicos
Python: 3.10 o superior.

Infraestructura: Docker Desktop con contenedores de Odoo y PostgreSQL activos.

Librerías principales:

pandas: Para la manipulación y limpieza de datos.

psycopg2-binary: Para la gestión de la conexión con PostgreSQL.

🚀 Procedimiento de Configuración
Sigue estos pasos para replicar el entorno y ejecutar la carga de datos:

1. Preparación del Entorno Docker
Asegúrate de que tus contenedores de Odoo y la base de datos están operativos. Puedes verificarlo con:

Bash
docker ps
El script está configurado para conectar por defecto al puerto 5432 con el usuario y contraseña odoo.

2. Instalación de Dependencias
Instala las librerías necesarias mediante pip:

Bash
pip install pandas psycopg2-binary
3. Preparación del Script
El archivo importar.py utiliza un diccionario de configuración para las credenciales de la base de datos.

Se ha implementado la lectura del CSV con codificación latin1 para garantizar la integridad de tildes y caracteres especiales (como la "ñ").

El script incluye una sentencia CREATE TABLE IF NOT EXISTS para automatizar la creación de la tabla import_centros.

4. Ejecución
Ejecuta el script desde la terminal de VS Code:

Bash
python importar.py
📈 Tareas Realizadas
[x] Conexión Robusta: Manejo de errores mediante bloques try/except.

[x] Tratamiento de Datos: Uso de Pandas para la carga eficiente del CSV.

[x] Automatización SQL: Creación automática de tablas y mapeo de datos mediante iloc.

[x] Integridad de Datos: Implementación de commit() al finalizar el bucle para asegurar la persistencia.

🖼️ Verificación del Proceso
A continuación se muestra la evidencia de la ejecución exitosa del script y la persistencia de los datos en PostgreSQL:

Nota: En la siguiente captura se observa la terminal con el mensaje de éxito y la consulta en pgAdmin, incluyendo la barra de tareas del sistema para validación de autoría.

📂 Estructura del Repositorio
importar.py: Script principal documentado.

listado.csv: Archivo fuente con los datos de los centros educativos.

README.md: Documentación del proyecto.
