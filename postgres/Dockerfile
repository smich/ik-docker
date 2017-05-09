FROM postgres

ENV POSTGRES_IK_PASSWORD 1k1n1s1sRulz
ENV POSTGRES_IK_USER inkinisis
ENV POSTGRES_IK_DB inkinisis_db

RUN apt-get update && apt-get install -y --no-install-recommends \
    apt-utils \
    sudo \
    vim

EXPOSE 5432

COPY docker-entrypoint-initdb.d /docker-entrypoint-initdb.d/