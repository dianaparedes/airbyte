FROM python:3.7-slim

# Bash is installed for more convenient debugging.
RUN apt-get update && apt-get install -y jq curl bash && rm -rf /var/lib/apt/lists/*

WORKDIR /airbyte/integration_code
COPY source_file ./source_file
COPY main.py ./
COPY setup.py ./
RUN pip install .

ENV AIRBYTE_ENTRYPOINT "python /airbyte/integration_code/main.py"
ENTRYPOINT ["python", "/airbyte/integration_code/main.py"]

LABEL io.airbyte.version=0.2.8
LABEL io.airbyte.name=airbyte/source-file
