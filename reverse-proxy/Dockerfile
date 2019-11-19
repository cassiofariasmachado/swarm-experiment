FROM nginx

COPY certs/domain.crt /root/certs/domain.crt
COPY certs/domain.key /root/certs/domain.key

# copy the config files
RUN rm /etc/nginx/conf.d/*

COPY conf.d/demo-api.conf /etc/nginx/conf.d/