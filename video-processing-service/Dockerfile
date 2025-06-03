FROM node:18
WORKDIR /app
COPY package*.json ./
RUN apt-get update && apt-get install -y ffmpeg
RUN npm install
COPY . .
EXPOSE 3000
CMD ["npm", "start"]

# # Stage 1: Build stage
# FROM node:18 AS builder

# # Set working directory in the container to /app
# WORKDIR /app

# # Copy package.json and package-lock.json into working directory
# COPY package*.json ./

# # Install any needed packages specified in package.json
# RUN npm install

# # Bundle app source inside the docker image
# COPY . .

# # Build the app
# RUN npm run build

# # Stage 2: Production stage
# FROM node:18

# # Install ffmpeg in the container
# RUN apt-get update && apt-get install -y ffmpeg

# # Set the working directory 
# WORKDIR /app

# # Copy package.json and package-lock.json
# COPY package*.json ./

# # Install only production dependencies
# RUN npm install --only=production

# # Copy built app from the builder stage
# COPY --from=builder /app/dist ./dist

# # Make port 3000 available
# EXPOSE 3000

# # Define command to run app using CMD which defines runtime
# CMD ["npm", "start", "serve"]