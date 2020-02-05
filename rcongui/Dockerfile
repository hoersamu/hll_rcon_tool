FROM node:13-stretch

WORKDIR /var/www

RUN apt-get update -y && apt-get install -y nginx
COPY nginx.conf /etc/nginx/sites-available/default

COPY . .

RUN npm install
ENV REACT_APP_API_URL /api/

RUN npm run build

CMD nginx -g 'daemon off;'