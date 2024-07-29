FROM mysql:8.0
# not a human, only for system
# /var/lib/mysql --> place where MySQL stores databases
RUN adduser -r expense
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions
# Below directories --> Change ownership as normal user
RUN chown -R expense:expense /var/lib/mysql /var/run/mysqld
COPY scripts/*.sql /docker-entrypoint-initdb.d/
# Until above we have root access from below we don't have root access
USER expense