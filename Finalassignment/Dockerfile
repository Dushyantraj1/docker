# First stage - build stage
FROM node:14-alpine as build
WORKDIR /app
COPY package.json /app/
RUN npm install
COPY . .
#RUN npm run build

FROM nginx:alpine
COPY --from=build /app/ /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

