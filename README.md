# OpenWeather Data Engineering Pipeline: Airflow, Docker & AWS

Ye ek end-to-end data engineering project hai jo real-time weather data ko handle karne ke liye banaya gaya hai. Is pipeline mein data extraction, transformation, aur loading (ETL) ke processes ko automate kiya gaya hai.

## 🚀 Project Overview

Is project ka maqsad ek scalable aur automated environment banana hai jo:

1. **OpenWeather API** se real-time data fetch karta hai.
2. **Python (Pandas)** ka use karte hue data ko transform karta hai (Temperature conversion, Timestamp formatting).
3. Data ko do jagah load karta hai:
* **AWS S3 Bucket:** Archive aur long-term storage ke liye (Data Lake).
* **PostgreSQL:** Structured format mein analytical queries ke liye (RDBMS).


4. Poore workflow ko **Apache Airflow** ke zariye schedule aur orchestrate kiya jata hai.

## 🛠 Tech Stack

* **Orchestration:** Apache Airflow
* **Containerization:** Docker & Docker Compose
* **Cloud Storage:** AWS S3
* **Database:** PostgreSQL v16
* **Monitoring:** pgAdmin 4
* **Language:** Python 3.11
* **Libraries:** Pandas, Boto3, S3fs

## 📂 Project Structure

```text
docker_exp/
├── dags/                    # Airflow DAG files (ETL Logic)
├── logs/                    # Airflow container logs
├── config/                  # Airflow configuration
├── plugins/                 # Custom plugins
├── sql/                     # SQL scripts (Table creation)
├── Dockerfile               # Custom Airflow image with dependencies
├── docker-compose.yaml      # Multi-container setup
└── README.md                # Project documentation

```

## ⚙️ Setup & Installation

### 1. Prerequisites

* Aapke system mein **Docker** aur **Docker Compose** installed hona chahiye.
* Ek **AWS Account** aur **IAM User** (S3 Full Access ke saath).
* **OpenWeather API Key**.

### 2. Configuration

Ek `.env` file project root mein banayein aur usme apni credentials add karein:

```bash
AIRFLOW_UID=50000
AWS_ACCESS_KEY_ID=apki_access_key
AWS_SECRET_ACCESS_KEY=apki_secret_key
OPENWEATHER_API_KEY=apki_api_key

```

### 3. Execution

Containers ko start karne ke liye:

```bash
docker-compose up -d --build

```

### 4. Airflow UI Setup

`http://localhost:8080` par login karein (Username/Password: `airflow`) aur ye connections configure karein:

* **`weathermap_api`**: (HTTP Connection) - Host: `https://api.openweathermap.org`
* **`postgres_default`**: (Postgres Connection)

## 📊 Pipeline Workflow

1. **HttpSensor:** Sabse pehle check karta hai ke Weather API available hai ya nahi.
2. **Extraction:** API se JSON format mein raw data fetch kiya jata hai.
3. **Transformation:** Python logic ke zariye data clean kiya jata hai aur units convert kiye jate hain.
4. **Loading:** - Data ko timestamped CSV file ke taur par **AWS S3** mein upload kiya jata hai.
* Wahi data **PostgreSQL** table mein insert kiya jata hai taake pgAdmin ke zariye query kiya ja sake.



## 📈 Future Enhancements

* Data quality checks (Great Expectations) implement karna.
* Multiple cities ka weather data process karna.
* Monitoring ke liye Grafana dashboard integrate karna.

---

**Developed by:** [clouddatawithosama](https://github.com/clouddatawithosama)

*Cloud Data Engineering Enthusiast*