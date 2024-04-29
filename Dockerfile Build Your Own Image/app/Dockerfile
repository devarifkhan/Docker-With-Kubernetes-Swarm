# - Use 'node' official image , with the alpine 6.x branch
FROM node:6-alpine
# - this app listens on port 3000, but the container should launch on port 80
# - so it will respond to http://localhost:80 on your computer
EXPOSE 3000
# - then it should use alpine package manager to install tini: 'apk add --update tini'
RUN apk add --update tini
# - then it should create directory /usr/src/app for app files with 'mkdir -p /usr/src/app'
RUN mkdir -p /usr/src/app
# - Node uses a "package.json" file to define what its app is and what it needs
WORKDIR /usr/src/app
COPY package.json /usr/src/app/
# - then it needs to run "npm install" to install the app dependencies
# - to keep clean and small, run 'npm cache clean --force' after above
# - then it needs to copy in all files in the current directory
RUN npm install && npm cache clean
# - then it needs to copy in all files in the current directory
COPY . .
# - then it needs to start container with command 'tini -- node ./bin/www'
CMD [ "tini", "--", "node", "./bin/www" ]

