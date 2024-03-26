FROM debian:bookworm

RUN apt update && apt install -y postgresql-client-15 && rm -rf /var/lib/apt/lists/*
COPY insert.sql /insert.sql

CMD ["psql"]
