# Build extensions
FROM postgres:16.4 AS builder
WORKDIR /build

RUN apt-get update && apt-get install -y \
  build-essential \
  git \
  curl \
  && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/pgpartman/pg_partman && \
    cd pg_partman && \
    make NO_BGW=1 install

# Build final image
FROM postgres:16.4

COPY --from=builder /usr/share/postgresql/16/extension/pg_partman* /usr/share/postgresql/16/extension/
