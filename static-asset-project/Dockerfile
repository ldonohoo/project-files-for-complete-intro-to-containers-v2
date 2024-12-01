FROM node:20 AS dependency-load
RUN mkdir /app
WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build

FROM nginx:alpine AS runtime
COPY --from=dependency-load /app/dist /usr/share/nginx/html
