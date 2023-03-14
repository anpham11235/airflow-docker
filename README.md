# docker-compose edit CeleryExecutor --> LocalExecutor
curl -LfO 'https://airflow.apache.org/docs/apache-airflow/2.5.1/docker-compose.yaml'

Some directories in the container are mounted, which means that their contents are synchronized between your computer and the container.

./dags - you can put your DAG files here.

./logs - contains logs from task execution and scheduler.

./plugins - you can put your custom plugins here.

mkdir -p ./dags ./logs ./plugins
run this if you use Linux:
echo -e "AIRFLOW_UID=$(id -u)" > .env

Initialize the database
On all operating systems, you need to run database migrations and create the first user account. To do this, run.

docker compose up airflow-init

docker compose up -d