# nginx
cd /nginx 
docker build . -t nginx1


cd ../php
docker build . -t php1

docker run -d --rm --name php php1
docker run -d --rm --link php:php --name nginx nginx1

