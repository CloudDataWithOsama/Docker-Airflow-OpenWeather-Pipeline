# S3 Bucket
    Create S3 Bucket
    •   s3-openweather-oh

# Open Weather API Key:
	https://openweathermap.org/
    •	Create your account
	https://home.openweathermap.org/api_keys
    •	Create and Copy your Active Key

# IAM Role
    airflow-openweather-role
    •	AmazonEC2FullAccess
    •	AmazonS3FullAccess

# IAM USER
    airflow-openweather-user
    •	AdministratorAccess
    Create access key
    •	Check --> Command Line Interface (CLI) – & – Confirmation
    •	Copy your Access Key ID & Secret Access Key

# EC2
    Create EC2 Instance
    •	Instance type: t2.xlarge
    •	Add Security Group Rule: Port (4000-38888)
    •	Configure Storage (16 GB)
    •	Add Role: airflow-openweather-role