# Docker Networks

Docker networks enable communication and connectivity between containers running on the same host or across multiple hosts within a Docker swarm. 
They allow containers to interact securely and efficiently with each other and with external resources, such as other containers, services, and external networks.

Here are some key aspects of Docker networks:

**Default Bridge Network:** When you install Docker, a default bridge network named "bridge" is created automatically. 
By default, Docker containers are attached to this bridge network unless you specify a different network explicitly. Containers connected to the same bridge network can communicate with each other using their IP addresses.

**User-Defined Bridge Networks:** Docker allows you to create custom bridge networks. 
User-defined bridge networks offer better isolation and security between containers. You can create multiple custom bridge networks to group related containers together, and containers within the same network can communicate with each other using container names or custom DNS names.

**Host Network:** Docker also provides a special network mode called the host network, where a container shares the host's network namespace. 
In this mode, the container uses the host's network stack directly and does not have its own network namespace, resulting in less isolation but potentially better performance for network-intensive applications.

**Overlay Network:** Overlay networks are used in Docker swarm mode, which is Docker's built-in orchestration and clustering solution. 
Overlay networks enable containers running on different Docker hosts to communicate with each other, even if they are hosted on different physical machines. This facilitates seamless communication in a distributed and scalable environment.

**Macvlan Network:** Macvlan allows you to assign a unique MAC address to each container, making them appear as separate physical devices on the network. 
This can be useful for scenarios where containers need to be directly reachable on the local network.

**IPv6 Support:** Docker networks also support IPv6, enabling containers to use IPv6 addresses and communicate over IPv6 networks.

By leveraging Docker networks, you can build sophisticated and interconnected containerized applications. 
Networks facilitate secure communication between containers while providing isolation and flexibility in how containers are grouped and scaled. Whether you're running a simple application or orchestrating a complex microservices architecture, Docker networks are an essential tool for efficient container communication.

## Important commands

1. ``` docker network ls ```

This is for a list of networks 

You will get generally 

```bash
NETWORK ID     NAME      DRIVER    SCOPE
3fd5a1ddb946   bridge    bridge    local
44d577fb2668   host      host      local
e939ca1c65c9   none      null      local
```

2. ``` docker network inspect <NAME>```

This will give the status of containers running on a network.

3. ``` docker network create <YOUR_NETWORK_NAME> ```

This will create a network with the name given.

4. ``` docker container -d --name <ANY_NAME> --network <YOUR_NETWORK_NAME> <DOCKER_IMAGE> ```

This will run the container in a specified network. 

-d is the short form for detach.

5. ``` docker network disconnect ```

This is to remove a container from the network.

## DNS

Docker DNS (Domain Name System) is a feature provided by Docker that enables containerized applications to resolve domain names to IP addresses and communicate with other containers or external resources using human-readable domain names.

When you run containers within Docker, they are assigned their own network namespace, separate from the host system. By default, Docker automatically configures a DNS resolver for each container, allowing them to resolve domain names to IP addresses within their isolated network environment.

Key aspects of Docker DNS include:

**Name Resolution:** Each container launched within Docker has access to a built-in DNS resolver, which allows it to resolve domain names to IP addresses. This enables containers to communicate with each other or with external resources using domain names instead of raw IP addresses.

**Hostnames:** Docker automatically assigns a hostname to each container based on the container's name. For example, if you start a container with the name "webserver," its hostname will be "webserver." This simplifies communication between containers, as they can address each other using the assigned hostnames.

**Custom Network Names:** When you create a custom bridge network or overlay network in Docker, each container attached to that network can communicate with other containers in the same network using container names or hostnames.

**Internal DNS Resolution:** Docker's DNS resolver also handles DNS resolution for internal Docker networks. Containers can communicate with each other by their container names or custom hostnames, making the network configuration more user-friendly.

**Host System Resolution:** By default, Docker containers use the DNS settings from the host system. This allows containers to resolve domain names that are resolvable by the host system's DNS resolver. If necessary, you can also configure custom DNS settings for Docker containers.

Overall, Docker DNS simplifies networking between containers by providing a built-in DNS resolution mechanism. This feature allows containers to communicate with each other using familiar domain names and hostnames, making it easier to manage and scale containerized applications.  
