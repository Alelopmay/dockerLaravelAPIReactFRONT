# Build Stage
FROM node:alpine AS build
RUN apk add --no-cache git
RUN git clone https://github.com/Alelopmay/ProyectoConApi.git
#RUN npm install -g vite
WORKDIR /ReactViteSkel
#COPY vite-project/package*.json ./
RUN npm install
#COPY vite-project .
RUN npm run build
 
# Production Stage
FROM nginx:stable-alpine AS production
COPY --from=build /ProyectoConApi/apiReact/dist /usr/share/nginx/html