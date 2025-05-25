# movieboxapi

The MovieBox  is a cloud-native, microservices-based backend system designed to handle the real-time needs of a modern movie ticket booking application. Built using Spring Boot, Spring Cloud, JPA, and MySQL, the platform ensures high availability, scalability, and consistent user experience through intelligent service orchestration and concurrency control mechanisms.

The architecture follows a modular microservices pattern, where each core domain (e.g., movie management, booking, notifications) is isolated into separate services that can scale and deploy independently. Using Eureka for service discovery, Spring Cloud Gateway for routing, and LoadBalancer for even traffic distribution, the system ensures both fault tolerance and efficient request handling.

Here are all the microservices in your MOVIEBOX project and their use cases:

---

### 1. **Location Service**
**Use Cases:**
- Manage locations (cities, areas, etc.).
- Retrieve all locations.
- Retrieve all theatres in a specific location.
- Integrate with Theatre Service to fetch theatres by location.

---

### 2. **Theatre Service**
**Use Cases:**
- Manage theatres (add, update, delete, list).
- Retrieve theatres by name or location.
- Integrate with Screening Service to fetch screenings for a theatre.

---

### 3. **Screening Service**
**Use Cases:**
- Manage movie screenings (show timings, etc.).
- Retrieve all screenings.
- Retrieve screenings by theatre.
- Integrate with Seat Service to fetch available seats for a screening.

---

### 4. **Seat Service**
**Use Cases:**
- Manage seats for each screening.
- Check seat availability and status (booked/available).
- Lock seats for a user for a limited time.
- Book or release seats.

---

### 5. **Service Registry**
**Use Cases:**
- Register and discover all microservices.
- Enable dynamic service lookup for inter-service communication.

---

### 6. **Gateway**
**Use Cases:**
- Provide a single entry point for all client requests.
- Route requests to appropriate microservices.
- Handle cross-cutting concerns (authentication, logging, etc.).

---

**Summary Table:**
  
| Microservice      | Main Use Cases                                                                 |
|-------------------|-------------------------------------------------------------------------------|
| Location Service  | Manage locations, list locations, get theatres by location                     |
| Theatre Service   | Manage theatres, get theatres by name/location, get screenings by theatre      |
| Screening Service | Manage screenings, get screenings by theatre, get seats by screening           |
| Seat Service      | Manage seats, check/book/lock/release seats                                    |
| Service Registry  | Service registration and discovery                                             |
| Gateway           | API gateway, routing, cross-cutting concerns                                   |
