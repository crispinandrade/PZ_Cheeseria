# Angular Application
FROM node AS angular
WORKDIR /app/ui
COPY package.json ./
RUN npm install
COPY . ./
EXPOSE 4200
CMD /app/ui/node_modules/.bin/ng serve --host 0.0.0.0
