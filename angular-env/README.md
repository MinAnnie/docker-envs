# Using Docker and Docker Compose to Develop with Angular 17

This project utilizes Docker and Docker Compose to enhance Angular application development. By containing all the
necessary dependencies and configurations, it provides a cleaner and more efficient development environment.

## Requirements

Ensure that you have the following programs installed on your machine:

- [Docker](https://www.docker.com/get-started) (version 20.10 or newer)
- [Docker Compose](https://docs.docker.com/compose/install/) (version 1.27 or newer)

## Project Structure

In this project, you will find the following structure:

```
.
├── compose.yaml 
├── dockerfiles
│   ├── Dockerfile
│   └── Dockerfile.lazyvim
└── README.md

```

- **`docker-compose.yaml`**: This file orchestrates the creation and configuration of the services needed to run your
  Angular application in Docker containers.

- **`dockerfiles`**: In this folder, you will find two Dockerfile entries:
    - **`Dockerfile`**: Contains all the necessary installations to work with Angular in Docker. This Dockerfile is
      designed to run and develop Angular applications without needing additional installations on your local machine.
      You can use your preferred IDE or text editor to work with the code.

    - **`Dockerfile.lazyvim`**: This Dockerfile is configured to allow you to work entirely in containers using LazyVim,
      a Neovim configuration that enhances the development experience. This approach enables you to enjoy an enriched
      development environment directly in the container, without needing to install anything on your machine.

## Usage

1. **Build and Run the Container**: From the root of the project, execute the following command to build and run the
   services defined in `docker-compose.yaml`:

   ```bash
   docker-compose up --build
   ```
   This command will download the necessary images and create the defined containers.

2. Development with LazyVim: To work with LazyVim, access the container using the following command:

```bash
   docker-compose up --build
   ```

This will open an interactive terminal inside the container where you can use nvim and benefit from the LazyVim
configuration.

3. Using Angular CLI: Inside the container, you can use the Angular CLI to create new Angular applications. To do this,
   you can run:

```bash
   ng new my-angular-app
   ```

After creating your application, navigate to the application directory and start the development server with the
following command:

```bash
   ng serve --host 0.0.0.0
   ```

## Considerations

Environment Variables: If you need to define environment variables for your application, consider creating a .env file
at the root of the project. Docker Compose will automatically load these variables.

```dotenv
UID=000
GID=000
```

## Contributions

If you would like to contribute to this project, feel free to open an issue or create a pull request on GitHub.
