# Use NodeJS as the base image
FROM node:14

# Special directory within the container 
WORKDIR /app

# Copy the package.json file into the directory
COPY package.json .

# Install all necessary dependencies 
RUN npm install

# Copy the rest of the code - copy everything from the same place as the dockerfile, to “where i am now” in the container
COPY . .

# Exposing the port
EXPOSE 3000

# Execute the app with Node command
CMD ["node", "app.mjs"]