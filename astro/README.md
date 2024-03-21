**Astro Dockerfile**

This Dockerfile builds a production-ready image for an Astro application.

### Usage

To build the image, run the following command:

```
docker build -t astro .
```

To run the image, run the following command:

```
docker run -p 4321:4321 astro
```

The application will be available at `http://localhost:4321`.

### Environment Variables

The following environment variables can be used to configure the application:

* `PORT`: The port that the application will listen on. Defaults to `4321`.

### Contributing

Contributions are welcome! Please open an issue or pull request if you have any questions or suggestions.

### License

This project is licensed under the Apache License, Version 2.0. See [LICENSE](../LICENSE) for the full license text.