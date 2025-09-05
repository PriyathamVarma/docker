# 📘 Docker Basics

## 🔹 Container

* A **container** is a running instance of an image.
* Think of it as a **box** 🥡 holding your app + dependencies, isolated from the host.
* You can start, stop, delete, and restart containers anytime.

---

## 🔹 Image

* An **image** is a **blueprint** for containers.
* Built from a **Dockerfile** (set of instructions).
* Read-only snapshot containing code, dependencies, and environment.

---

## 🔹 Registry

* A **registry** is a storage/repository for images.
* Example: **Docker Hub** (public), AWS ECR, GCP Artifact Registry.
* You can `push` and `pull` images between your system and the registry.

---

## 📝 Basic Dockerfile for React App

```dockerfile
# Step 1: Use official Node image
FROM node:18

# Step 2: Set working directory inside container
WORKDIR /app

# Step 3: Copy package.json first (better caching for dependencies)
COPY package.json package-lock.json ./

# Step 4: Install dependencies
RUN npm install

# Step 5: Copy the rest of the app
COPY . .

# Step 6: Expose port (React dev server runs on 3000)
EXPOSE 3000

# Step 7: Start the React app
CMD ["npm", "start"]
```

---

## 🚀 Steps to Create a React Container

1. **Build the Docker image**

   ```bash
   docker build -t docker-react .
   ```

2. **Run the container (development mode)**

   ```bash
   docker run --rm -it -p 3000:3000 -e HOST=0.0.0.0 docker-react
   ```

   * `-p 3000:3000` → maps container port 3000 → localhost:3000
   * `-e HOST=0.0.0.0` → makes React dev server accessible from host

3. **Open the app in browser**

   ```
   http://localhost:3000
   ```

4. **List running containers**

   ```bash
   docker ps
   ```

5. **Stop container (if running in background)**

   ```bash
   docker stop <container-id-or-name>
   ```

---

## 📤 Pushing to Docker Hub

### 1) Tag the image

```bash
docker tag docker-react:latest <your-username>/docker-react:latest
```

Example:

```bash
docker tag docker-react:latest varmavatsavaye/docker-react:latest
```

### 2) Log in to Docker Hub

```bash
docker login
```

* Username: your Docker Hub username
* Password: your password OR a Personal Access Token (if you have 2FA enabled)

### 3) Push to Docker Hub

```bash
docker push <your-username>/docker-react:latest
```

Example:

```bash
docker push varmavatsavaye/docker-react:latest
```

### 4) Use it anywhere

Anyone can now pull and run your image:

```bash
docker pull <your-username>/docker-react:latest
docker run -p 3000:3000 <your-username>/docker-react:latest
```

Example:

```bash
docker pull varmavatsavaye/docker-react:latest
docker run -p 3000:3000 varmavatsavaye/docker-react:latest
```
