FROM nginx:latest
WORKDIR /home/
COPY ./nginx.conf /etc/nginx/
COPY ./server.c /home/server.c
COPY ./run.sh /home/run.sh
RUN apt-get update && apt-get install -y gcc spawn-fcgi libfcgi-dev; \
    chown -R nginx:nginx /etc/nginx/nginx.conf; \
    chown -R nginx:nginx /var/cache/nginx; \
    chown -R nginx:nginx /home; \
    rm -rf /var/lib/apt/lists
USER nginx
ENTRYPOINT ["sh","run.sh"]
