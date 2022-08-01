FROM apache/spark:v3.3.0

USER root

RUN mkdir -p /opt/spark-data

WORKDIR /opt/spark-data

ENV SPARK_MASTER_WEBUI_PORT=8080 \
    SPARK_LOG_DIR=/opt/spark/work-dir/spark-data/logs \
    SPARK_MASTER_LOG=/opt/spark/work-dir/spark-data/logs/spark-master.out \
    SPARK_WORKER_LOG=/opt/spark/work-dir/spark-data/logs/spark-worker.out \
    SPARK_WORKER_WEBUI_PORT=8080 \
    SPARK_WORKER_PORT=7000 \
    SPARK_MASTER="spark://spark-master:7077" \
    SPARK_WORKLOAD="master"=value

COPY ./entrypoint.sh /
RUN chmod a+x /entrypoint.sh

ENTRYPOINT [ "/bin/sh" ]

