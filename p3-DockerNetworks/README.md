# DockerNetworks
---

# Docker Networks

Docker networks provide a mechanism to allow communication between Docker containers and with external networks. Docker supports multiple networking modes, each with its own characteristics and use cases. Below is a list of common Docker network types along with their definitions:

## 1. **Bridge Network**
   - **Definition**: The default network type for Docker containers. When you create a container, it is automatically connected to this network unless specified otherwise. Containers on the same bridge network can communicate with each other by their IP address or container name.
   - **Use Case**: Ideal for container-to-container communication on a single host.

## 2. **Host Network**
   - **Definition**: The container shares the host’s network stack and receives the same IP address as the host machine. There is no network isolation between the container and the host.
   - **Use Case**: Used for performance optimization where network isolation is not needed or is detrimental.

## 3. **None Network**
   - **Definition**: This type disables networking for the container entirely. The container has no access to any network interfaces.
   - **Use Case**: Useful when network access is not needed, such as for isolated batch jobs.

## 4. **Overlay Network**
   - **Definition**: Allows containers running on different Docker hosts (in a Swarm cluster or using Docker Enterprise) to communicate securely. The network is distributed across multiple Docker hosts.
   - **Use Case**: Used for multi-host communication in Docker Swarm or Docker Enterprise environments.

## 5. **Macvlan Network**
   - **Definition**: Assigns a MAC address to each container, which makes it look like a physical device on the network. This network type allows containers to appear as separate devices on the network.
   - **Use Case**: Useful for applications requiring direct control over network traffic, such as network appliances or legacy applications.

## 6. **Custom Bridge Network**
   - **Definition**: A user-defined bridge network that allows more advanced control over container communication, including DNS-based container discovery and isolation from the default bridge network.
   - **Use Case**: Recommended when you need more flexibility than the default bridge network provides.

---
