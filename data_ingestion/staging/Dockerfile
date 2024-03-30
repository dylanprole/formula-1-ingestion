FROM python:3.9.1

ARG USER_CODE_PATH=/home/src/data_ingestion

COPY /tmp/google/google-service-account.json ${USER_CODE_PATH}/google-service-account.json

ENV GOOGLE_APPLICATION_CREDENTIALS=${USER_CODE_PATH}/google-service-account.json
ENV GCP_GCS_BUCKET=taxi-rides-ny-412407-data-lake-development

RUN apt-get install wget
RUN pip install requests pandas pyarrow google-cloud-storage

WORKDIR /app
COPY ingest_f1_data.py ingest_f1_data.py

ENTRYPOINT [ "python", "ingest_f1_data.py" ]