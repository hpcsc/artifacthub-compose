# Build extensions
FROM postgres:16.4 AS builder
ARG TARGETARCH
WORKDIR /build

RUN apt-get update && apt-get install -y \
  curl \
  && rm -rf /var/lib/apt/lists/*

RUN curl -sSL "https://github.com/jackc/tern/releases/download/v2.2.1/tern_2.2.1_linux_${TARGETARCH}.tar.gz" | \
    tar -xvzf -

# Build final image
FROM postgres:16.4

WORKDIR /app

COPY --from=builder /build/tern /usr/local/bin/tern
COPY db.conf ./
