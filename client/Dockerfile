FROM node:lts-alpine@sha256:96cc8323e25c8cc6ddcb8b965e135cfd57846e8003ec0d7bcec16c5fd5f6d39f AS dependencies
WORKDIR /dependencies

COPY package*.json ./

RUN npm install


FROM node:lts-alpine@sha256:96cc8323e25c8cc6ddcb8b965e135cfd57846e8003ec0d7bcec16c5fd5f6d39f AS build
WORKDIR /build

COPY --from=dependencies /dependencies ./
COPY . .

RUN npm run build

FROM nginx:stable-alpine@sha256:35e3238f2f0925a505d5d697df9a9148db9a0c78e89fd2e253919047b3cec824
COPY --from=build /build/build /usr/share/nginx/html


COPY <<-"EOT" /etc/nginx/nginx.conf
worker_processes  1;

events {
    worker_connections  1024;
}


http {
    server {
        listen 80;
        server_name  localhost;

        root   /usr/share/nginx/html;
        index  index.html index.htm;
        include /etc/nginx/mime.types;

        gzip on;
        gzip_min_length 1000;
        gzip_proxied expired no-cache no-store private auth;
        gzip_types text/plain text/css application/json application/javascript application/x-javascript text/xml application/xml application/xml+rss text/javascript image/svg+xml;

        location ~* \.(js|css|png|jpg|jpeg|gif|svg|ico)$ {
          expires 7d;
        }

        location / {
            try_files $uri $uri/ /index.html;

            add_header Cache-Control 'no-store, no-cache, must-revalidate, proxy-revalidate, max-age=0';
            if_modified_since off;
            expires off;
            etag off;
        }
    }
}
EOT

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

