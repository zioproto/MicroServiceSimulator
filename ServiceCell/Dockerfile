FROM python:slim

RUN apt update
COPY requirements.txt /app/

WORKDIR /app

RUN pip install -r requirements.txt

EXPOSE 8080
EXPOSE 51313

COPY CellController.py ExternalServiceExecutor.py InternalServiceExecutor.py mub.proto mub_pb2.py \
mub_pb2_grpc.py start.sh ./

CMD [ "prometheus_multiproc_dir=/app", "/usr/local/bin/python3", "/app/CellController.py"]
