FROM python:3.9.1

ARG USER_CODE_PATH=/home/src/data_ingestion

COPY ./.keys/taxi-rides-ny-412407-d5f6d54a82a5.json ${USER_CODE_PATH}/.keys/taxi-rides-ny-412407-d5f6d54a82a5.json

ENV GOOGLE_APPLICATION_CREDENTIALS=${USER_CODE_PATH}/.keys/taxi-rides-ny-412407-d5f6d54a82a5.json
ENV GCP_GCS_BUCKET=taxi-rides-ny-412407-data-lake-production

RUN apt-get install wget
RUN pip install requests pandas pyarrow google-cloud-storage

WORKDIR /app
COPY ingest_f1_data.py ingest_f1_data.py

ENTRYPOINT [ "python", "ingest_f1_data.py" ]