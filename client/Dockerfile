## Build Phase
FROM node:alpine

WORKDIR '/app'
COPY package*.json ./

RUN npm install

# When running code in production environment straight copy of src code is okay, because we're not changing our code
COPY . .

RUN npm run build
# /app/build <-- all the stuff we care about

## Run Phase
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf

# command to copy over build folder into the nginx container
COPY --from=0 /app/build /usr/share/nginx/html
