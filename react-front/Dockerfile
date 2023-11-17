# Usa una imagen base de Node.js
FROM node:14

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

# Expone el puerto 80 en la imagen (esto es solo informativo, no es necesario para aplicaciones de una sola página)
EXPOSE 80

# Comando para ejecutar la aplicación cuando se inicia el contenedor
CMD ["npm", "start"]
