# Stage 1: Build
FROM node:14 as build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Stage 2: Serve
FROM nginx:alpine
COPY --from=build /app/dist/my-app-frontend /usr/share/nginx/html