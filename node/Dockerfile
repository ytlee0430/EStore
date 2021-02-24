# pull official base image
FROM node:13.12.0-alpine
# ENV HTTP_PROXY "http://127.0.0.1:3001"
# ENV HTTPS_PROXY "http://127.0.0.1:3001"

# set working directory
WORKDIR /app

# add `/app/node_modules/.bin` to $PATH
ENV PATH /app/node_modules/.bin:$PATH

# install app dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm config set registry http://registry.npmjs.org/
# RUN npm config set proxy="http://127.0.0.1:3001"
# RUN npm config set https-proxy="http://127.0.0.1:3001"
RUN npm install 
RUN npm install react-scripts@3.4.1 -g --silent

# add app
COPY . ./

EXPOSE 8080
# start app
CMD ["npm", "start"]