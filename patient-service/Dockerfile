FROM node:20-alpine

WORKDIR /app
COPY package*.json ./
RUN npm install --only=production
COPY . .
HEALTHCHECK --interval=30s --timeout=5s --start-period=10s --retries=3 \
  CMD wget -qO- http://localhost:3000/health || exit 1doc
EXPOSE 3000
CMD ["npm", "start"]