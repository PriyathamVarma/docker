# Docker Container Volumes

Containers are immutable. So when the container is re-deployed what happens to the databases. 
This is where persistent data come sin where the data is carried over. 

This is done using: Data Volumes and Bind Mounts

Data volumes - make special location outside of container.

Command in Dockerfile:

```dockerfile 
VOLUME <Path_To_Folder>
```

