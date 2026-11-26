# Component Diagram Audit

## 1. Purpose

The purpose of this audit is to verify the consistency of the UML Component Diagram with the previous models of the Library Reservation System.

The audit checks component responsibilities, interfaces, dependencies, external integrations, and the system boundary.

## 2. Consistency Checks

### 2.1 Consistency with the ER Data Model (Lab 1)

The ER model defines the main data entities: Reader, Author, Category, Book, BookCopy, Reservation, Loan, and Librarian.

The component model includes the Library Database and Data Access Layer, which provide storage and controlled access to these entities.

**Result:** Consistent.

### 2.2 Consistency with Requirements and Use Cases (Lab 2)

The Reservation Service supports UC-01: Reserve a Book Copy. It checks the availability of a selected book copy and processes reservation requests.

The Catalog Service provides book and book copy information required by this use case.

**Result:** Consistent.

### 2.3 Consistency with Sequence Diagrams (Lab 3)

The sequence diagrams describe interactions between the Reader, Reservation UI, Reservation Service, BookCopy, and Reservation.

The component model assigns these responsibilities to the User Interface, API / Backend, Reservation Service, and Data Access Layer.

The Notification Service supports the confirmation step.

**Result:** Consistent.

### 2.4 Consistency with the Activity Diagram (Lab 4)

The activity diagram describes checking availability, creating a reservation, updating the book copy status, and sending a confirmation message.

The component model supports these activities through the Reservation Service, Data Access Layer, and Notification Service.

The external Email Provider delivers the confirmation email. The process does not require the Reader to reply.

**Result:** Consistent.

## 3. Top 3 Discrepancies and Resolutions

### Discrepancy 1: Data Entities vs. Software Components

The ER model defines data entities, while the component diagram defines software components. Their responsibilities are different and must not be confused.

**Resolution:** The Library Database stores the ER entities, while the Data Access Layer provides controlled access to the stored data.

### Discrepancy 2: Reservation Logic Distribution

Previous models describe reservation behavior and interactions but do not define the complete software architecture responsible for processing requests.

**Resolution:** The API / Backend handles incoming requests, while the Reservation Service implements reservation-related business logic.

### Discrepancy 3: Notification Delivery Mechanism

The Activity Diagram describes sending a confirmation message to the Reader but does not specify the external delivery mechanism.

**Resolution:** The Notification Service is responsible for initiating notification delivery through the external Email Provider. The Reader does not need to respond for the reservation process to continue.

## 4. Interfaces and Dependencies

The component diagram identifies provided and required interfaces between internal components and the external Email Provider.

The system boundary separates internal components from external services.

The main dependencies are:

- User Interface → API / Backend;
- API / Backend → Catalog, Reservation, and Loan Services;
- Reservation Service → Data Access Layer and Notification Service;
- Catalog Service → Data Access Layer;
- Loan Service → Data Access Layer;
- Data Access Layer → Library Database;
- Notification Service → External Email Provider.

## 5. Conclusion

The component diagram is consistent with the previous models of the Library Reservation System.

The identified differences clarify the distribution of software responsibilities and the external notification mechanism without contradicting the existing requirements, data model, interaction scenarios, or business process.