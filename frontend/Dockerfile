From node:18-alpine

# Set the working directory
WORKDIR /app


# Copy package.json and package-lock.json files to the container
COPY package.json package-lock.json ./

# Copy the .env file to the container
COPY .env ./

# Install dependencies
RUN npm install

# Copy files from directory to container
COPY . .


# Expose default react port
EXPOSE 5173

# Start the application
CMD ["npm", "run", "dev", "--", "--host", "--port", "5173"]