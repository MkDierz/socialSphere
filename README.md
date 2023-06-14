# SocialSphere

SocialSphere is a scalable and modular microservice architecture-based social media platform. The architecture consists of eight services: Authentication, User, Post, Interaction, Tag, User Analytics, Post Analytics, and Home Feed service. Each service is responsible for a specific functionality, making SocialSphere highly maintainable and easy to update or scale. The backend is built with Express.js and Prisma as an ORM, and PostgreSQL is used as the database.

SocialSphere services are dockerized, meaning each service has its own Dockerfile and they are orchestrated using a `docker-compose.yaml` file.

## Services

1. **Authentication Service**: Manages user authentication processes such as user registration, login, token verification, password recovery, and logout.
2. **User Service**: Manages user profiles including bio, username, full name, cover image, and friend list. Users can view their own profile or those of their friends. Also handles friend requests.
3. **Post Service**: Handles all operations related to posts such as creating, editing, viewing, deleting, and searching. Each post maintains a "last interaction date," which updates when someone interacts with the post (via the Interaction Service).
4. **Interaction Service**: Manages interactions with a post or a comment, including creating, viewing, deleting, and managing likes and comments. This service also provides a list of posts that a user has liked.
5. **Tag Service**: Manages all operations related to tags associated with a post, including creating, editing, viewing, and deleting them.
6. **User Analytics Service**: Records and displays user-specific analytics. This includes logging user login information such as IP, device, and time, and recording search analytics.
7. **Post Analytics Service**: Records and displays analytics related to post interactions, including data on post views, likes, and comments.
8. **Home Feed Service**: Aggregates posts from a user's friends and any posts where their friends have interacted, sorted by the "last interaction date."

## Getting Started

Clone the repository to your local machine.

```bash
git clone --recursive https://github.com/MkDierz/SocialSphere.git
```

The `--recursive` argument is used to clone all the submodule repositories.

### Prerequisites

Ensure you have the following installed on your system:

- Docker
- Docker Compose
- Node.js (For development)

### Running the project

Navigate into the root directory of the project and use Docker Compose to build and run the application:

```bash
docker-compose up --build
```

This will spin up all the services, and they will start communicating with each other.

### Stopping the project

To stop running all services, use:

```bash
docker-compose down
```

## Documentation

Further documentation on each service is available within the respective service's directory. The documentation includes information on the service's API endpoints, data models, and specific setup or running instructions.

## Contributing

Please refer to the CONTRIBUTING.md file for information about how to contribute to SocialSphere.

## License

This project is licensed under the MIT License. See the LICENSE.md file for details.
