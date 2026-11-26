# Defense — Library Reservation System Component Diagram

## 1. Intent and Acceptance Criteria

The purpose of this laboratory work is to describe the software architecture of the Library Reservation System using a UML Component Diagram.

The diagram represents the main software components, their responsibilities, provided and required interfaces, dependencies, system boundary, and external integrations.

The model is considered complete if all required architectural elements are represented and the component relationships are consistent with the project specification and previous laboratory models.

## 2. Main Components

The component diagram includes the following elements:

- **User Interface** — provides interaction for Readers and Librarians.
- **API / Backend** — receives requests from the user interface and routes them to business services.
- **Catalog Service** — provides book, author, category, and book copy information.
- **Reservation Service** — processes reservation requests and coordinates reservation operations.
- **Loan Service** — manages book loans and returns.
- **Notification Service** — initiates the delivery of reservation confirmation notifications.
- **Data Access Layer** — provides controlled access to stored information.
- **Library Database** — stores the system's library data.
- **External Email Provider** — delivers confirmation emails outside the system boundary.

## 3. Top-3 Discrepancies and Resolutions

1. **Data entities and software components:** The ER model describes data entities, while the component diagram describes software modules. The Data Access Layer and Library Database clarify how software components access and store the data.

2. **Reservation logic distribution:** Previous models describe reservation behavior but do not define the complete software architecture. The API / Backend handles incoming requests, while the Reservation Service manages reservation business logic.

3. **Notification delivery:** The Activity Diagram describes sending a confirmation message but does not specify the external delivery mechanism. The Notification Service initiates notification delivery through the Email Delivery Interface provided by the External Email Provider.

## 4. Consistency with Previous Laboratory Work

The component diagram was reviewed against the previous laboratory models:

- **Lab 1 — Domain and Data Model (ER):** the database supports the entities defined in the data model.
- **Lab 2 — Use Case Diagram and Scenarios:** the Reservation Service supports the book copy reservation use case.
- **Lab 3 — Sequence Diagrams:** the Reservation Service and Notification Service represent the responsibilities involved in the reservation interactions.
- **Lab 4 — Activity Diagram:** the architecture supports availability checking, reservation creation, data updates, and confirmation notification delivery.

The component model describes the software structure that supports the previously modeled system behavior.

## 5. Final Result

The UML Component Diagram describes the main architectural structure of the Library Reservation System, including its internal components, interfaces, dependencies, system boundary, and external email integration.

The model, specification, and audit were reviewed for consistency with the project requirements and previous laboratory work.