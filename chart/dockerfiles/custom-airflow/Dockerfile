FROM apache/airflow:2.1.0-python3.8
#ENV NB_USER="maker" \
#    HOME="/home/${NB_USER}/projects"
# Airflow
#ENV AIRFLOW_DEPS="async,amazon,celery,cncf.kubernetes,docker,dask,elasticsearch,ftp,grpc,hashicorp,http,ldap,google,microsoft.azure,mysql,postgres,redis,sendgrid,sftp,slack,ssh,statsd,virtualenv"
#ENV AIRFLOW_VERSION="2.1.0"
#ARG PYTHON_VERSION=$(python --version | cut -d " " -f 2 | cut -d "." -f 1-2)
#ENV CONSTRAINT_URL="https://raw.githubusercontent.com/apache/airflow/constraints-${AIRFLOW_VERSION}/constraints-3.8.txt"

USER root
COPY ./requirements.txt .
#RUN mkdir ${HOME} && \
RUN sudo -E apt-get  update && sudo -E apt-get upgrade -y && \
    sudo -E apt-get install -y --no-install-recommends libsasl2-dev libkrb5-dev && \
    sudo -E apt-get install -y gcc python3-dev python3-pip libxml2-dev libxslt1-dev zlib1g-dev g++ libmysqlclient-dev && \
    sudo -E apt-get install -y unixodbc-dev && \
    pip install  -r ./requirements.txt
USER "airflow"
#WORKDIR "{$HOME}"
