FROM redis:5.0.4-alpine3.9
COPY sysctl.conf /etc/sysctl.conf

CMD ["redis-server", "--appendonly", "yes"]