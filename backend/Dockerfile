FROM node:18-alpine
WORKDIR /app
COPY package.json ./
COPY package-lock.json ./
RUN npm install
COPY . .
ENV PORT=5000
EXPOSE 5000
CMD ["npm", "start"]
