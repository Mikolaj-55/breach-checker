FROM nginx:alpine
LABEL maintainer="Mikolaj-55@users.noreply.github.com"
LABEL autor="Mikołaj Bembnista"
LABEL data="2026-11-06"
RUN apk add --no-cache nodejs npm && npm install -g htmlhint
COPY . /usr/share/nginx/
RUN date > /usr/share/nginx/html/build.txt
RUN htmlhint /usr/share/nginx/html/index.html
EXPOSE 80