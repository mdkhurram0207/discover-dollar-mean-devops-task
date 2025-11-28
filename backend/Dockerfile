FROM node:18-alpine

WORKDIR /usr/src/app

# Install only dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the backend code
COPY . .

# MongoDB connection (your app should read this)
ENV MONGO_URL=mongodb://mongo:27017/meanapp

# Backend port
EXPOSE 3000

# Start the server
CMD ["npm", "start"]
