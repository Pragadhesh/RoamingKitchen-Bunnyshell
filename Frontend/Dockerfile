# Base image
FROM node:14-alpine

# Set working directory
WORKDIR /app

# Install app dependencies
COPY package.json package-lock.json ./
RUN npm install

# Copy app source code
COPY . .

# Build the React app
RUN npm run build

# Set environment variables
ARG REACT_APP_GOOGLE_MAPS_API_KEY
ENV REACT_APP_GOOGLE_MAPS_API_KEY=$REACT_APP_GOOGLE_MAPS_API_KEY
ENV PORT=3000
ENV HOST=0.0.0.0

# Expose the app port
EXPOSE $PORT

# Start the app
CMD ["npm", "start"]