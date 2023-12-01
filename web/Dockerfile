# ==== CONFIGURE =====
# Use a Node 16 base image
FROM node:16-alpine 
COPY package*.json ./
COPY src/ ./src/
COPY public/ ./public/
RUN npm ci 
# Build the app
RUN npm run build
# Expose the port on which the app will be running (3000 is the default that `serve` uses)
EXPOSE 80
# Start the app
CMD [ "npx", "serve", "-s", "build" ]