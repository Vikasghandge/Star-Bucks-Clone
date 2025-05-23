# Use official Node.js image
FROM node:18

# Set working directory
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the app
COPY . .

# Build the app (React/Vue/etc.)
RUN npm run build

# Install Firebase CLI globally
RUN npm install -g firebase-tools

# Set Firebase project config
COPY firebase.json ./
COPY .firebaserc ./

# Serve the build folder using Firebase CLI
EXPOSE 5000
CMD ["firebase", "serve", "--only", "hosting", "--port", "5000"]
