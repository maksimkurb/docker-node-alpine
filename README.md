# Docker-node-alpine

Use this image like this

```docker
FROM maksimkurb/node-alpine:10 AS build

COPY . /app

RUN yarn install && \
    yarn run build

FROM nginx:1.15-alpine

COPY --from=build /app/build/ /var/www
COPY ./nginx.conf /etc/nginx/conf.d/default.conf
```
