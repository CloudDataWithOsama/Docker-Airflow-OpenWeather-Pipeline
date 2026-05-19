# AIRFLOW

```bash
                        -----> Open Weather
Airflow connection ---<
                        -----> Postgres

```

Admin ---> Connection ---> Add Connection

1.	Open Weather
   		Connection ID : weathermap_api
		Connection Type : HTTP

```bash
Host: https://api.openweathermap.org
```

2.	Postgres
   		Connection ID: postgres_default
  		Connection Type: Postgres

  		Host: postgres
  		Login: airflow
  		Password: airflow
  		Port: 5432
  		Database: airflow
