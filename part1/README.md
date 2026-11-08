# HBnB Evolution — Technical Documentation (Part 1)

## Introduction
Welcome to the technical documentation repository for **HBnB Evolution**, a scalable, modular clone of Airbnb. This project is developed as part of the Holberton School curriculum. The objective of Part 1 is to establish a solid architectural foundation—spanning 3-layer architecture, object-oriented domain modeling, and robust API workflows—before writing a single line of backend implementation code.

---

## High-Level Architecture (Task 0)
The application adheres strictly to a **3-Layer Architecture** (Presentation, Business Logic, and Persistence) to enforce separation of concerns. Communication between the presentation endpoints and the core domain is mediated through the **Facade Pattern** (`HBnBFacade`).

![High-Level Package Diagram](./images/high_level_package.png)

### Design Rationale
* **Presentation Layer:** Handles raw HTTP requests and returns formatted JSON responses via RESTful Flask endpoints.
* **Business Logic Layer:** Centralizes business rules, data validation, and core entities using `HBnBFacade` as the singular entry point.
* **Persistence Layer:** Encapsulates data storage logic using the Repository pattern (`DatabaseStorage`).

---

## Business Logic Layer (Task 1)
The core domain entities inherit from a foundational `BaseModel` class, ensuring consistent identifiers (`id`) and audit timestamps (`created_at`, `updated_at`) across the system.

![Detailed Class Diagram](./images/business_logic_class.png)

### Core Entities & Relationships
* **`BaseModel`:** Base class providing UUID generation and dictionary serialization (`to_dict()`).
* **`User`:** Represents application users (1-to-many relationship with `Place` and `Review`).
* **`Place`:** Represents a property listing managed by a User, mapping to multiple `Review` records and featuring a many-to-many relationship with `Amenity`.
* **`Review`:** User feedback linked to specific places.
* **`Amenity`:** Property features (e.g., Wi-Fi, Pool).

---

## API Interaction Flows (Task 2)
The following sequence diagrams illustrate how data travels across the architectural layers during standard API operations.

### 1. User Registration Workflow
![User Registration Sequence](./images/seq_user_registration.png)

### 2. Place Creation Workflow (`POST /places`)
![Place Creation Sequence](./images/seq_place_creation.png)

### 3. Review Submission Workflow
![Review Submission Sequence](./images/seq_review_submission.png)

### 4. Fetching Places Workflow (`GET /places`)
![Fetch Places Sequence](./images/seq_fetch_places.png)

---

## Author
Developed by Kevin Rodriguez, a Holberton School student as part of the HBnB Evolution project.