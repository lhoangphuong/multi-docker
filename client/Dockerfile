FROM node:alpile as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /ect/nginx/conf.d/default/conf
COPY --from=builder /app/build /usr/share/nginx/html