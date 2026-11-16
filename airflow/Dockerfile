FROM apache/airflow:2.8.1-python3.10

USER root
RUN apt-get update && apt-get install -y --no-install-recommends \
    openjdk-17-jre-headless \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

ENV JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

USER airflow
ENV PATH="/home/airflow/.local/bin:${JAVA_HOME}/bin:${PATH}"

RUN pip install --no-cache-dir apache-airflow-providers-apache-spark