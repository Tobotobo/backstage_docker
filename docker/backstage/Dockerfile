FROM node:20-bookworm-slim

WORKDIR /app
RUN yes '' | npx @backstage/create-app@latest

RUN sed -i \
    -e 's|  baseUrl: http://localhost:3000|  baseUrl: http://0.0.0.0:3000|' \
    -e 's|  baseUrl: http://localhost:7007|  baseUrl: http://0.0.0.0:7007|' \
    /app/backstage/app-config.yaml

WORKDIR /app/backstage
CMD ["yarn", "dev"]