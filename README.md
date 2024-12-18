
---

```markdown
# Storing DATA from the API to the Local Database using RestTemplet

A Spring Boot application that fetches user data from the [ReqRes API](https://reqres.in/api/users/) and stores it in a MySQL database. This project demonstrates how to integrate remote APIs with local databases using Spring Boot, RestTemplate, and JPA.

---

## Features

- Fetch user data from a remote API (https://reqres.in/api/users/).
- Store the data in a MySQL database using Spring Data JPA.
- Synchronize data with support for saving and updating records.
- Easy-to-configure properties for API and database integration.

---

## Technologies Used

- **Java 17**
- **Spring Boot 3.4.0**
- **Spring Data JPA**
- **RestTemplate**
- **MySQL** as the database
- **Maven** for project management

---

## Getting Started

### Prerequisites

1. Install Java 17 or higher.
2. Install MySQL and create a database named `user_sync_app`.
3. Configure the database connection in `application.properties`.

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/user_sync_app
spring.datasource.username=root
spring.datasource.password=yourpassword
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
```

---

### Project Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/UserSyncApp.git
   cd UserSyncApp
   ```

2. Build the project:
   ```bash
   mvn clean install
   ```

3. Run the application:
   ```bash
   mvn spring-boot:run
   ```

4. Check the `users` table in your MySQL database to see the synchronized data.

---

### How It Works

1. The application uses `RestTemplate` to fetch data from the ReqRes API.
2. The response is mapped to a `User` model using a DTO (`ApiResponse`).
3. The data is saved into a MySQL database using JPA's `saveAll` method.

---

## API Details

- The API used for this project is [ReqRes](https://reqres.in/).
- Endpoint: `https://reqres.in/api/users/`
- Fields fetched:
  - `id`
  - `email`
  - `first_name`
  - `last_name`
  - `avatar`

---

## Database Schema

Use the following query to create the `users` table:

```sql
CREATE TABLE users (
    id BIGINT PRIMARY KEY,
    email VARCHAR(255),
    first_name VARCHAR(255),
    last_name VARCHAR(255),
    avatar VARCHAR(255)
);
```

---

## Future Enhancements

- Implement scheduled synchronization using Spring's `@Scheduled` annotation.
- Add error handling for API failures.
- Create a front-end interface to display user data.

---

## Author

Created by **Abhishek Kumar**. Feel free to connect with me on [GitHub](https://github.com/abhishek-kr03)!
```

---

### **Steps to Push the Project to GitHub**

1. **Initialize Git in Your Project Directory:**
   ```bash
   git init
   ```

2. **Add Remote Repository:**
   ```bash
   git remote add origin https://github.com/your-username/UserSyncApp.git
   ```

3. **Add All Files:**
   ```bash
   git add .
   ```

4. **Commit the Changes:**
   ```bash
   git commit -m "Initial commit: UserSyncApp"
   ```

5. **Push to GitHub:**
   ```bash
   git branch -M main
   git push -u origin main
   ```

---
