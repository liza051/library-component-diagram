
# Specification — Library Reservation System Architecture

## 1. System Intent

The purpose of this specification is to describe the software architecture of the Library Reservation System using a UML Component Diagram.

The architecture identifies the main software components, their responsibilities, interfaces, dependencies, database access, and external integrations.

## 2. System Boundary

The Library Reservation System includes the user interface, API layer, business services, data access layer, and library database.

External services are located outside the system boundary and communicate with internal components through defined interfaces.

## 3. Main Components and Responsibilities

### 3.1 User Interface
- Provides an interface for Readers and Librarians.
- Allows readers to browse the catalog and reserve book copies.
- Allows librarians to manage books, copies, loans, and returns.
- Sends requests to the API layer.

### 3.2 API / Backend
- Receives requests from the user interface.
- Routes requests to the appropriate business services.
- Returns responses to the user interface.

### 3.3 Catalog Service
- Retrieves book and author information.
- Provides access to book categories.
- Provides information about physical book copies.

### 3.4 Reservation Service
- Processes book reservation requests.
- Checks the availability of selected book copies.
- Creates and manages reservations.
- Coordinates reservation status updates.

### 3.5 Loan Service
- Manages book loans and returns.
- Records issue dates, due dates, and return dates.
- Updates loan information.

### 3.6 Notification Service
- Sends reservation confirmation messages.
- Communicates with an external email provider.
- Does not require the Reader to respond to a notification.

### 3.7 Data Access Layer
- Provides controlled access to stored data.
- Executes data retrieval and modification operations.
- Separates business services from database implementation.

### 3.8 Library Database
- Stores Readers, Authors, Categories, Books, and BookCopies.
- Stores Reservations, Loans, and Librarians.
- Maintains relationships between library entities.

## 4. Interfaces

The architecture defines the following interfaces:

### Provided Interfaces
- Catalog API — provided by Catalog Service.
- Reservation API — provided by Reservation Service.
- Loan API — provided by Loan Service.
- Notification API — provided by Notification Service.
- Data Access Interface — provided by Data Access Layer.

### Required Interfaces
- User Interface requires API access.
- API / Backend requires Catalog, Reservation, and Loan services.
- Reservation Service requires Data Access and Notification interfaces.
- Catalog Service requires Data Access Interface.
- Loan Service requires Data Access Interface.
- Notification Service requires an external Email Provider.
- Data Access Layer requires database connectivity.

## 5. External Integrations

### Email Provider
- Located outside the system boundary.
- Receives notification requests from Notification Service.
- Delivers reservation confirmation emails to Readers.
- The system does not wait for the Reader to reply.

No payment or OAuth integration is included because these integrations are not required by the current system scope.

## 6. Main Dependencies

- User Interface depends on API / Backend.
- API / Backend depends on business services.
- Business services depend on Data Access Layer.
- Data Access Layer depends on Library Database.
- Notification Service depends on the external Email Provider.

## 7. Consistency with Previous Models

The architecture must remain consistent with:
- The ER data model from Lab 1.
- The use case and reservation scenarios from Lab 2.
- The interaction sequences from Lab 3.
- The reservation business process from Lab 4.

## 8. Modeling Notation

The architecture will be represented using a UML Component Diagram in Mermaid declarative syntax.

The diagram will show component responsibilities, provided and required interfaces, dependencies, external integration, and the system boundary.

