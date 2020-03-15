FROM node:6-alpine
ENV NODE_ENV production
RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories && apk update && apk upgrade && \
    apk add --no-cache bash git openssh 
RUN npm config set unsafe-perm true 
WORKDIR /app
COPY ./autopull/* /app/
RUN npm install github-webhook-handler
EXPOSE 9091
CMD node index.js
