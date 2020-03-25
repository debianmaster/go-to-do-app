FROM node:8.15.0 AS build-env
WORKDIR /app
ADD package.json /app
RUN npm install
ADD . /app
RUN npm run build

FROM nginx
COPY --from=build-env /app/build /etc/nginx/html
ENV PORT 3000
EXPOSE 3000
#ADD server /server
#COPY run.sh run.sh
ADD nginx.conf /etc/nginx/nginx.conf
#CMD ["./run.sh"]
