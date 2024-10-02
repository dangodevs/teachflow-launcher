# Project Name

This project is a microservices-based application that includes a gateway service, a utility service, and a database service. The gateway service handles incoming requests and communicates with the utility service via NATS messaging. The utility service performs various utility functions and interacts with a PostgreSQL database.

## Services

- **Gateway**: Handles incoming HTTP requests and communicates with other services.
- **Utility Service**: Provides utility functions and interacts with the database.
- **NATS Server**: Messaging server used for communication between services.
- **PostgreSQL Database**: Stores data for the utility service.

## Docker Setup

The project uses Docker for containerization. The [`docker-compose.yml`](docker-compose.yml) file defines the services and their configurations.

### Running the Services

To start the services, run:

```sh
docker-compose up
```

## Debugging

The project includes a VSCode configuration for debugging the gateway service in a Docker container. The configuration can be found in `.vscode/launch.json`.

## Git Submodules
### Steps to create Git Submodules

1. Create a new repository on GitHub
2. Clone the repository on the local machine
3. Add the submodule, where 'repository_url' is the URL of the repository and 'directory_name' is the name of the folder where you want to save the submodule (it should not exist in the project)
```
git submodule add <repository_url> <directory_name>
```
4. Add the changes to the repository (git add, git commit, git push)
Example:
```
git add .
git commit -m "Add submodule"
git push
```
5. Initialize and update submodules, when someone clones the repository for the first time, they should run the following command to initialize and update the submodules
```
git submodule update --init --recursive
```
6. To update the references of the submodules
```
git submodule update --remote
```

## Important
If you work in the repository that has the submodules, **first update and push** in the submodule and **then** in the main repository.

If you do it the other way around, the references of the submodules in the main repository will be lost and we will have to resolve conflicts.