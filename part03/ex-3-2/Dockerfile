FROM python:3.7-slim-stretch
WORKDIR /app
RUN pip install --user --upgrade yle-dl \
    && apt-get update \
    && apt-get install -y wget \
    && rm -rf /var/lib/apt/lists/*
ENV PATH "${PATH}:/root/.local/bin"
ENTRYPOINT ["yle-dl", "--destdir", "."]
CMD [""]
