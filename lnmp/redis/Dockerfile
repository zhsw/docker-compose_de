FROM redis:6

RUN mkdir /logs && chown redis:redis /logs
VOLUME /logs

CMD ["redis-server", "/usr/local/etc/redis/redis.conf"]
