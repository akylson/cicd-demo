FROM node:10
WORKDIR /usr/src/app
COPY package*.json ./

# copy app source code 

COPY . .

# Install packages or Copy sources code 
RUN npm install 

ENV PORT=5432
EXPOSE 5432

CMD [ "npm", "start" ]
