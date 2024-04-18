#Create image
docker build -t assets-server .

#Run container
docker run -d -p 83:80 -v /home/pi/vue3-doorbell-receiver/src/assets:/usr/share/nginx/html/assets --name assets-server assets-server

#Make it autostart
docker update --restart unless-stopped assets-server
