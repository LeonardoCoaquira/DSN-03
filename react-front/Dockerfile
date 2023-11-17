# Etapa de construcción (Build Stage) con imagen completa de Node.js
FROM node:14 AS build

# Establece el directorio de trabajo en /app
WORKDIR /app

# Copia el package.json y package-lock.json a la imagen
COPY package*.json ./

# Instala las dependencias del proyecto
RUN npm install

# Copia el contenido del directorio actual al directorio de trabajo en la imagen
COPY . .

# Compila la aplicación React para producción
RUN npm run build

# Etapa de producción con imagen alpine
FROM nginx:alpine

# Copia los archivos de construcción de la etapa anterior a la ubicación correcta en el servidor nginx
COPY --from=build /app/build /usr/share/nginx/html

# Expone el puerto 80 en la imagen (por si acaso, aunque no es necesario para aplicaciones de una sola página)
EXPOSE 3000

# Comando para iniciar nginx cuando se inicia el contenedor
CMD ["nginx", "-g", "daemon off;"]