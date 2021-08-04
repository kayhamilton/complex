FROM node:alpine

# Current working directory
WORKDIR '/app'

# Install some dependencies
COPY ./package.json ./
RUN npm install

COPY . .

# Default command
CMD ["npm", "run", "start"]