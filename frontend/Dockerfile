# Stage 1: Build the Angular app
FROM node:16 AS build

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json (if present) into the container
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the entire Angular project into the container
COPY . .

# Build the Angular app for production
RUN npm run build --prod

# Stage 2: Serve the Angular app with Nginx
FROM nginx:alpine

# Copy the Angular build output from the build stage into Nginx HTML folder
COPY --from=build /app/dist/angular-16-crud /usr/share/nginx/html

# Expose port 80 to serve the app
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]

