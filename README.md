Pep_2_Dag
# Proyecto de Base de Datos Espacial

Este repositorio contiene un proyecto para determinar los predios óptimos para la instalación de un gimnasio en la comuna de Estación Central, utilizando un modelo espacial y PostgreSQL/PostGIS.

## Descripción del Proyecto

El objetivo principal del proyecto es identificar los mejores predios para instalar un gimnasio, empleando análisis espacial y variables relevantes. El script Python ejecuta procesos de configuración y geoprocesamiento en una base de datos PostgreSQL/PostGIS, incluyendo:

1. Creación de esquemas y almacenamiento de datos espaciales.
2. Ejecución de un modelo espacial basado en datos proporcionados y definidos por el usuario.
3. Generación de resultados almacenados en la base de datos.

## Requerimientos

### Dependencias

- Python 3.8+
- PostgreSQL con PostGIS habilitado
- Bibliotecas de Python:
  - `certifi 2024.12.14`
  - `et_xmlfile 2.0.0`
  - `GeoAlchemy2 0.16.0`
  - `geopandas 1.0.1`
  - `greenlet 3.1.1`
  - `numpy 2.2.0`
  - `openpyxl 3.1.5`
  - `packaging 24.2`
  - `pandas 2.2.3`
  - `pip 24.0`
  - `psycopg2 2.9.10`
  - `pyodbc 5.2.0`
  - `pyogrio 0.10.0`
  - `pyproj 3.7.0`
  - `python-dateutil 2.9.0.post0`
  - `pytz 2024.2`
  - `setuptools 65.5.0`
  - `shapely 2.0.6`
  - `six 1.17.0`
  - `SQLAlchemy 2.0.36`
  - `typing_extensions 4.12.2`
  - `tzdata 2024.2`

### Instalación de dependencias

Ejecute el siguiente comando para instalar las dependencias desde el archivo `requirements.txt`:

```bash
pip install -r requirements.txt
```

### Archivos incluidos

- **`main.py`**: Script Python principal que automatiza la configuración, procesamiento y ejecución del modelo.
- **`config.json`**: Archivo de configuración para especificar credenciales y detalles de la base de datos.
- **`scripts.sql`**: Archivo SQL con procesos y geoprocesos necesarios.
- **Datos de ejemplo**: Capas espaciales descargadas desde el IDE y el INE (¡cargar manualmente en PostGIS o proporcionar mediante `main.py`).

### Configuración de la Base de Datos

Cree una base de datos PostgreSQL habilitada con PostGIS. Configure `config.json` con los siguientes detalles:

```json
{
    "database": {
        "db_type": "postgresql",
        "db": "pep_2",
        "schema": "entradas",
	    "host": "localhost",
	    "port": "5432",
	    "passwd": "postgres",
	    "user": "postgres"
    }
}
```

### Ejecución del Proyecto

1. Clone el repositorio:

```bash
git clone https://github.com/tu_usuario/Pep2_Dag.git
cd Pep2_Dag
```

2. Configure el archivo `config.json` con los datos de conexión a la base de datos.

3. Instale las dependencias desde `requirements.txt`:

```bash
pip install -r requirements.txt
```

4. Ejecute el script principal:

```bash
python main.py
```

Esto realizará las siguientes acciones:
- Crear esquemas y cargar datos en la base de datos.
- Ejecutar el archivo SQL.
- Generar los resultados en el esquema configurado.

### Archivos SQL

El archivo `scripts.sql` contiene:
- Geoprocesos necesarios para calcular la accesibilidad, densidad poblacional, y otras variables relevantes.
- Procesos para seleccionar los predios óptimos.

### Datos de ejemplo

Incluya capas espaciales relevantes como:
- Predios de la comuna de Estación Central.
- Datos normativos asociados a los predios (zonificación, restricciones).
- Datos adicionales (densidad poblacional, ingresos promedio).

Ejemplo:
- Shapefiles: `Calles.shp`, `CentrosDeportivos.shp`, `DatMan.shp`, `PrediosEC.shp`

### Ejemplo de Uso

Al ejecutar el script con los datos de ejemplo y el archivo SQL, el sistema genera un esquema con resultados que pueden ser consultados en PostgreSQL.

```sql
SELECT * FROM resultados.predios_optimos;
```

## Contribución

1. Fork este repositorio.
2. Cree una nueva rama:
   ```bash
   git checkout -b feature/nueva_caracteristica
   ```
3. Realice sus cambios y haga commit:
   ```bash
   git commit -m "Agrego nueva característica"
   ```
4. Envie un pull request.

## Licencia

Este proyecto está licenciado bajo [Licencia MIT](LICENSE).
