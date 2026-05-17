FROM node:26-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production


FROM node:26-alpine
WORKDIR /app
COPY --from=build /app/node_modules ./node_modules
COPY src ./src
COPY package.json ./

EXPOSE 3000
CMD ["npm", "start"]