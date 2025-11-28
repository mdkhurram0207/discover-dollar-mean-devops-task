# Stage 1 – Build Angular App
FROM node:18-alpine as build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

# Build Angular app (you already confirmed this works locally)
RUN npm run build --prod

# Stage 2 – Serve using Nginx
FROM nginx:alpine

# Adjust path if your dist folder name is different
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
