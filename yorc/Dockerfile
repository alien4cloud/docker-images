FROM ystia/yorc:4.2.0

RUN apk add jq && \
    apk add openjdk8 && \
    apk add util-linux && \
    apk add gettext && \
    cd /usr/local/bin && \
    curl -O https://storage.googleapis.com/kubernetes-release/release/v1.14.1/bin/linux/amd64/kubectl && \
    chmod a+x kubectl && \
    mkdir /usr/local/spark && \
    cd /usr/local/spark && \
    curl -O http://archive.apache.org/dist/spark/spark-3.0.1/spark-3.0.1-bin-hadoop2.7.tgz && \
    tar xzf spark-3.0.1-bin-hadoop2.7.tgz && \
    rm spark-3.0.1-bin-hadoop2.7.tgz && \
    ln -s /usr/local/spark/spark-3.0.1-bin-hadoop2.7/bin/spark-submit /usr/bin/spark-submit && \
    echo export SPARK_HOME=/usr/local/spark/spark-3.0.1-bin-hadoop2.7 >> /var/yorc/.profile && \
    addgroup consul yorc
