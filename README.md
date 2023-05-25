# SharePix
share pix is a online site to upload, display and download the images.

# Idea

**version 1 : one user uploads the pic and upon request others can download the pic.


# Inital database model:



1. **User**
   - id: Unique identifier for the user
   - username: User's username
   - email: User's email address
   - password: User's password (encrypted)
   - created_at: Timestamp of user registration

2. **Picture**
   - id: Unique identifier for the picture
   - title: Title of the picture
   - description: Description of the picture
   - file_name: Name of the picture file
   - file_path: Path to the picture file on the server
   - user_id: Foreign key referencing the user who uploaded the picture
   - uploaded_at: Timestamp of picture upload

3. **Request**
   - id: Unique identifier for the request
   - requester_id: Foreign key referencing the user who made the request
   - owner_id: Foreign key referencing the user who owns the requested picture
   - picture_id: Foreign key referencing the requested picture
   - created_at: Timestamp of the request creation

With this updated data model, you can implement the functionality where a user can request a picture from another user. The "Request" entity captures the relationship between the requester, the owner of the requested picture, and the requested picture itself.

When a user makes a request, you can create a new entry in the "Request" collection, including the IDs of the requester, owner, and the picture being requested. The "created_at" field stores the timestamp of the request creation.

Additionally, you can consider adding status fields to the "Request" entity to track the status of each request, such as "pending," "accepted," or "declined." This can provide further functionality for managing requests.

Remember to adjust the data model and relationships according to your specific project requirements.


# file sturcture

**version 1: 
src
├── main
│   ├── java
│   │   └── com
│   │       └── yourcompany
│   │           ├── config
│   │           │   └── SecurityConfig.java
│   │           ├── controller
│   │           │   └── PictureController.java
│   │           ├── dto
│   │           │   ├── PictureRequestDTO.java
│   │           │   ├── PictureResponseDTO.java
│   │           │   └── RequestDTO.java
│   │           ├── exception
│   │           │   ├── CustomExceptionHandler.java
│   │           │   └── ErrorResponse.java
│   │           ├── model
│   │           │   ├── Picture.java
│   │           │   ├── Request.java
│   │           │   └── User.java
│   │           ├── repository
│   │           │   ├── PictureRepository.java
│   │           │   ├── RequestRepository.java
│   │           │   └── UserRepository.java
│   │           ├── service
│   │           │   ├── PictureService.java
│   │           │   ├── RequestService.java
│   │           │   └── UserService.java
│   │           └── Application.java
│   └── resources
│       ├── static
│       └── application.properties
└── test
    └── java
        └── com
            └── yourcompany
                ├── controller
                │   └── PictureControllerTest.java
                ├── service
                │   ├── PictureServiceTest.java
                │   ├── RequestServiceTest.java
                │   └── UserServiceTest.java
                └── repository
                    ├── PictureRepositoryTest.java
                    ├── RequestRepositoryTest.java
                    └── UserRepositoryTest.java


# sprint plan:

Sure! Here's an adjusted timeline for a one-month sprint to deliver the first version of your picture-sharing website:

**Sprint 1:**

**Week 1:
- Set up the project structure and environment.
- Define the data model and create the necessary backend modules (models, repositories, services).
- Implement user registration and authentication functionality.

**Week 2:
- Develop the frontend login and registration pages.
- Implement JWT-based authentication and authorization on the backend.
- Write unit tests for the authentication and user-related functionality.

**Week 3:
- Implement picture upload functionality on the backend.
- Create the frontend page for uploading pictures.
- Write unit tests for the picture upload functionality.

**Week 4:
- Implement picture retrieval functionality on the backend.
- Develop the frontend page for browsing and searching pictures.
- Write unit tests for the picture retrieval functionality.

During this sprint, focus on the core features of user registration, authentication, picture upload, and retrieval. It's important to prioritize functionality over additional features or refinements to ensure timely delivery.

After the one-month sprint, you can conduct a review of the completed features and gather feedback for further iterations and improvements. This will allow you to iterate and add more features in subsequent sprints based on the feedback and requirements of your users.

Remember to allocate time for documentation, code refactoring, and bug fixing throughout the sprint to maintain code quality and ensure a stable initial release.

As always, adapt the timeline based on your team's capacity and the specific requirements of your project.
