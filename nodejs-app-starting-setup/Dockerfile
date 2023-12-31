# Contains the set of instructions for our own image

# Build my image on the node image 
FROM node

# Setting the working directory
# By default the working directory is the root directory of the file system
# All the subsequent commands will be executed in the /app directory
WORKDIR /app

# Tell docker which files on local machine should go into the image
# Copy the 'package.json' file before copying the sourcecode
# The reson behind doing this is, docker follows the layer architecture
# All the steps (lines) in the dockerfile are layers and cached
# Once a single layer is changed, then that layer and all other layesr after that will be executed 
# Unless a 'package.json' change, any other code change will not require 'npm install'
# Hence, initially resolve the dependencies and copy the source code after that
# Then, the dependency resolving will not take place for fundemental code changes unless 'package.json' changes
COPY package.json /app

# RUN vs CMD
# RUN executes during the image building time
# CMD executes during the container creation time
# CMD requires an array of command splitted as Strings
# If you don't specify a CMD then the CMD of the base image will be executed
# If none of the CMD is found then it will throw an error

# Run necessary commands during the image build
# Since the 'WORKDIR /app', we can run the 'npm install' without any problem
RUN npm install

# Tell docker which files on local machine should go into the image
# '. .'' - Specify two paths
#   First '.' - Path outside of the container where the files should be copied into the image (All the file and subfolders)
#   Second '.'' - Path inside the image where the files should be stored (root)
#COPY . .
#   First '.' - Path outside of the container where the files should be copied into the image (All the file and subfolders)
#   Second '/app'' - Path inside the image where the files should be stored (/app directory - It will be created if it does not exist)
# Since the 'WORKDIR /app', we can easily run 'COPY . .' or 'COPY . ./' which will copy into '/app' (Same execution as providing the absolute path)
COPY . /app

# Specify the port (Expose from the container)
# This is only for documentation purposes ('EXPOSE 80' is optional yet a best practice)
# ATTENTION: The most important part is running the docker container exposing the ports (Example:- docker run -p 80:80 .....)
#            '80:80' - First '80' means which local port, Second '80' means which internal port
#            '3000:80' - First '3000' means which local port, Second '80' means which internal port
EXPOSE 80

# Start the server when the container is starting
CMD ["node", "server.js"]

