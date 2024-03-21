This repository contains two Dockerfiles for a Go application:

* **Dockerfile**: Builds a production-ready image for your Go application.
* **Dockerfile.dev**: Optimized Dockerfile for development with hot reloading.

### Building the Production Image

1. Navigate to the `golang` directory in your project.
2. Build the production image:

```
docker build -t your-image-name .
```

**Replace `your-image-name` with the desired name for your image.**

### Running the Production Image

```
docker run -p 8080:8080 your-image-name
```

This will run your application on port `8080` of the container.

### Development Workflow

For development, use the `Dockerfile.dev` and `docker-compose.dev.yml`. They leverage the `air` tool for hot reloading and Docker Compose to manage the application and its dependencies.

1. Build the development image:

```
docker build -t golang-dev -f Dockerfile.dev .
```

2. Start the application with Docker Compose:

```
docker compose -f docker-compose.dev.yml up
```

This will start the application in a container with hot reloading enabled. Any changes made to your local files will be reflected in the running application.

**Note:**

* The `-f` flag specifies the Docker Compose configuration file to use.
* You can also use `docker compose up -d` to start the application in detached mode.

### Environment Variables

The production image exposes the following environment variable:

* `PORT`: The port that the application will listen on. Defaults to `8080`.

### Contributing

Contributions are welcome! Please open an issue or pull request if you have any questions or suggestions.

### License

This project is licensed under the Apache License, Version 2.0. See [LICENSE](../LICENSE) for the full license text.

**Additional Notes:**

* The `docker-compose.dev.yml` file defines a network named `go_network`. This network is used to connect the application container to the database container.
* The `volumes` section in the `docker-compose.dev.yml` file mounts the local project directory (`./`) to the `/app` directory within the container. This ensures that any changes made to your local files are reflected in the running application.
* The `ports` section in the `docker-compose.dev.yml` file exposes port `4000` of the container to the host machine. This allows you to access the application on `http://localhost:4000`.
