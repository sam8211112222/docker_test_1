1) Create appropriate images for both apps  
A:   docker build .  
2) Launch a container for each created image   
A:   docker run -p 8000:3000 -d --rm IMAGE_ID  
3) Re-create both containers and assign names to both containers.
   Use these names to stop and restart both containers.   
A: docker run -p 8000:3000 -d  --name nodeApp IMAGE_ID  && docker stop nodeApp    
  (如果改成在container沒有使用的時候就會自動刪除了 docker run -p 8000:3000 -d -rm --name nodeApp IMAGE_ID)
4) Clean up (remove) all stopped (and running) containers, clean up all created images.  
A: docker rm CONTAINER_NAME && docker images && docker rmi IMAGE_ID    
5) Re-build the images - this time with names and tags assigned to them.
A: docker build -t node-demo:latest .
6) Run new containers based on the re-built images, ensuring that the containers
      are removed automatically when stopped.
A:  docker run -p 8000:3000 -d --rm --name nodeApp node-demo:latest 

