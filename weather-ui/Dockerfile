FROM node:10.24 as build-deps
RUN yarn install
RUN yarn build

FROM nginx:1.21-alpine
COPY --from=build-deps build /usr/share/nginx/html
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
