# ==== CONFIGURE =====
# Use a Node 16 base image
FROM node:16-alpine 
WORKDIR /app
COPY . .
RUN npm ci 
# Build the app
RUN npm run build
ENV NODE_ENV production
# Expose the port on which the app will be running (3000 is the default that `serve` uses)
EXPOSE 80
# Start the app
CMD [ "npx", "serve", "build" ]