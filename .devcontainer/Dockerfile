FROM mcr.microsoft.com/vscode/devcontainers/python:3.12-bullseye

RUN apt-get update && apt-get install -y \
		gcc libgdal-dev gdal-bin \
		python3-pip \
		python3-venv \
		&& rm -rf /var/lib/apt/lists/*

ENV GDAL_CONFIG=/usr/bin/gdal-config

#upgrade pip
RUN pip install --upgrade pip

WORKDIR /workspace

COPY requirements.txt .

RUN pip install -r requirements.txt

EXPOSE 8080 8000

CMD ["bash"]