ARG AIRFLOW_VERSION=3.0.6
FROM apache/airflow:${AIRFLOW_VERSION}-python3.10
ARG AIRFLOW_VERSION=3.0.6

USER root
RUN apt-get update && apt-get install -y --no-install-recommends \
    openjdk-17-jre-headless \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

USER airflow
RUN pip install --no-cache-dir \
    "apache-airflow==${AIRFLOW_VERSION}" \
    apache-airflow-providers-apache-spark \
    --constraint "https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-3.10.txt"