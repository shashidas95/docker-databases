FROM postgres:15-alpine

COPY ./my-postgres.conf /etc/postgresql/postgresql.conf

CMD ["postgres", "-c", "config_file=/etc/postgresql/postgresql.conf"]