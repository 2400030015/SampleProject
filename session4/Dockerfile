# ---------- Builder Stage ----------
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install

# ---------- Runtime Stage ----------
FROM node:20-alpine
WORKDIR /app

# Copy node_modules from builder
COPY --from=builder /app/node_modules ./node_modules

# Copy application code
COPY . .

EXPOSE 3000
CMD ["node", "index.js"]
