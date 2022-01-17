FROM node:14.17.0-alpine3.13
#   Create a group named 'app' and create a system user named 'app'
RUN addgroup app && adduser -S -G app app
#   Set the created user 'app' as the current user and use it to run all the next commands
USER app
#   Set our working directory as /app
WORKDIR /app
#   Using our app user, make a directory named 'data'
RUN mkdir data
#   Copy all files that ends with .json i.e. package.json & package-lock.json
COPY package*.json .
#   Run npm install command to install all dependencies if anything has changed about our package files else use cache
RUN npm install
#   Copy all files inside current dir
COPY . .
#   Set an env var named 'API_URL'
ENV API_URL=http://api.myapp.com/
#   Set 3000 as the port to use to run our app
EXPOSE 3000
#   Execute form : - in this process, no shell or terminal is needed, it is run directly.. THIS IS RECOMMENDED
#   This also makes it faster to clean up resources when we stop the container
CMD ["npm", "start"]
#   Shell form : - in this process, the container will run this in a shell terminal or command prompt
#   CMD npm start
