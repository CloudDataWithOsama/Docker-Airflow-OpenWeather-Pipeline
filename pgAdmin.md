## Query Tool Workspace

### Connect to the Server
•	Server name: Airflow Postgres
•	Host name/address: postgres
•	Port: 5432
•	Database: airflow
•	User: airflow
•	Password: airflow
Connect & Open Query Tool

### Create Table in PostgreSQL:

```bash
CREATE TABLE IF NOT EXISTS weather_data (
    id SERIAL PRIMARY KEY,
    city VARCHAR(50),
    description VARCHAR(100),
    temperature_f FLOAT,
    feels_like_f FLOAT,
    min_temp_f FLOAT,
    max_temp_f FLOAT,
    pressure INTEGER,
    humidity INTEGER,
    wind_speed FLOAT,
    time_of_record TIMESTAMP,
    sunrise TIMESTAMP,
    sunset TIMESTAMP
);

```

### Check Data

```bash
SELECT * FROM weather_data:

```