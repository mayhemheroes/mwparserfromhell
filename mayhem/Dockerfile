# Build Stage
FROM python:3.11-slim

RUN apt-get update && apt-get install -y \
    clang \
    git \
    gcc \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

RUN pip install atheris

ADD . /src
WORKDIR /src
ENV SETUPTOOLS_SCM_PRETEND_VERSION=1.0.0
RUN python3 -m pip install .

CMD ["/src/mayhem/fuzz_parse.py"]
