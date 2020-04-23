FROM node:12.16.2-alpine3.11 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:1.17.10-alpine
COPY --from=build /app/dist /usr/share/nginx/html
EXPOSE 80