# Base image
FROM node:20-alpine

# Set working directory
WORKDIR /app

# Install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy source files
COPY . .

# Build the app
RUN npm run build

# Expose port (Nest default: 3000)
EXPOSE 3000

# Start the app
CMD ["npm", "run", "start:dev"]
