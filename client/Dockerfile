FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm insatll
COPY . .
RUN npm run bunild

EROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
