FROM node:12 AS build

COPY package.json ./
COPY yarn.lock ./
RUN yarn install
COPY ./ ./
RUN yarn build

FROM nginx:stable
COPY --from=build /public /usr/share/nginx/html