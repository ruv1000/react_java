FROM node:10 as builder
WORKDIR /app
COPY ./react-app /app/
RUN npm install
RUN npm run build
# RUN ping 8.8.8.8

FROM nginx:1.15.7-alpine
RUN rm -rf /usr/share/nginx/html/*
COPY --from=builder /app/build /usr/share/nginx/html
COPY ./nginx/nginx.conf /etc/nginx/conf.d/default.conf




