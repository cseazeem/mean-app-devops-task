# Step 1: Build the Angular app
FROM node:16 AS build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build --prod

# Step 2: Serve with nginx
FROM nginx:alpine
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html
