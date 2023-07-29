FROM python:3.8-slim@sha256:b5f119fec364eb215bd0fc8b32e84d3909b5dc849f933e0473cdd633784b9193

ENV PYTHONUNBUFFERED True

WORKDIR /app

COPY ./requirements.txt ./requirements.txt

# pandas installed from ubuntu repos to avoid building C extensions
RUN pip install -r requirements.txt

COPY get_secret.py /app/get_secret.py
COPY entry-point.sh /app/entry-point.sh
COPY mlflow_auth.py /app/mlflow_auth.py

ENTRYPOINT ["/usr/bin/env", "bash", "/app/entry-point.sh"]

EXPOSE 8080
