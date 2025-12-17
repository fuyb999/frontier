FROM nginx:1.25.2
LABEL maintainer="AuthZed <support@authzed.com>"
EXPOSE 3000
ENV PORT=3000

ENTRYPOINT ["./docker-entrypoint-wrapper.sh"]
CMD []

COPY ./contrib/generate-config-env.sh .
COPY ./contrib/test-nginx-conf.sh .
COPY ./contrib/test-config-env.sh .
COPY ./contrib/nginx.conf.tmpl .
COPY ./contrib/docker-entrypoint-wrapper.sh .
RUN bash ./test-nginx-conf.sh

#COPY --from=playground-builder /app/build/ /usr/share/nginx/html/
COPY build/ /usr/share/nginx/html/
