 **Next.js Dockerfile**

This Dockerfile builds a production-ready image for a Next.js application.

### Key Features

- Multi-stage build for lean image size
- Alpine Linux base image for a minimal footprint
- Production-ready environment variables
- Optimized for security by running as a non-root user

### Building the Image

1. Navigate to the `next` directory in your project.
2. Build the image:

```
docker build -t nextjs-app .
```

### Running the Image

```
docker run -p 3000:3000 nextjs-app
```

This will run your Next.js application on port `3000` of the container. Access it at `http://localhost:3000`.

### Environment Variables

- **NODE_ENV**: Set to `production` for optimized performance.
- **NEXT_TELEMETRY_DISABLED**: Set to `1` to disable Next.js telemetry.
- **PORT**: The port that the application will listen on. Defaults to `3000`.

### Contributing

Contributions are welcome! Please open an issue or pull request if you have any questions or suggestions.

### License

This project is licensed under the Apache License, Version 2.0. See [LICENSE](../LICENSE) for the full license text.
