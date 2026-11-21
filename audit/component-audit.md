# Component Diagram Audit

## 1. Purpose

The purpose of this audit is to verify the consistency of the software architecture model with the previous models of the Library Reservation System.

The audit checks component responsibilities, dependencies, interfaces, and the system boundary.

## 2. Consistency Checks

### 2.1 Consistency with the ER Data Model (Lab 1)

The architecture includes a Library Database and a Data Access Layer that support the entities defined in the ER model: Reader, Author, Category, Book, BookCopy, Reservation, Loan, and Librarian.

The software components do not replace the data entities. They provide access to and manage the data.

**Result:** Consistent.

### 2.2 Consistency with Requirements and Use Cases (Lab 2)

The Reservation Service supports the `UC-01: Reserve a Book Copy` use case. It checks the availability of a selected book copy and creates a reservation.

The Catalog Service provides book and book copy information required by the reservation process.

**Result:** Consistent.

### 2.3 Consistency with Sequence Diagrams (Lab 3)

The architecture includes the Reservation Service and Notification Service, which correspond to the main responsibilities described in the reservation interaction scenarios.

The API / Backend component provides an entry point for requests from the user interface.

**Result:** Consistent.

### 2.4 Consistency with the Activity Diagram (Lab 4)

The architecture supports the activities shown in the reservation process:
- checking book copy availability;
- creating a reservation;
- updating reservation-related data;
- sending a confirmation notification.

The Notification Service uses an external Email Provider to deliver confirmation messages.

**Result:** Consistent.

## 3. Top 3 Discrepancies and Resolutions

### Discrepancy 1: Data Entities vs. Software Components

The ER model describes data entities, while the component diagram describes software modules.

**Resolution:** The Data Access Layer and Library Database were included to show how software components access and store the entities from the ER model.

### Discrepancy 2: Reservation Logic Distribution

Previous models describe the reservation process, but they do not fully specify the software architecture responsible for handling requests.

**Resolution:** The API / Backend and Reservation Service were included to separate request handling from business logic.

### Discrepancy 3: Notification Delivery Mechanism

The Activity Diagram shows the Notification Service sending a confirmation to the Reader, while the component model introduces an external Email Provider.

**Resolution:** The Email Provider was added as an external integration. This clarifies how notifications are delivered without changing the original business process.

## 4. Interfaces and Dependencies

The diagram identifies provided and required interfaces between the main components.

The system boundary separates internal components from the external Email Provider.

The main dependencies are:
- User Interface → API / Backend;
- API / Backend → business services;
- Business services → Data Access Layer;
- Data Access Layer → Library Database;
- Notification Service → external Email Provider.

## 5. Conclusion

The component diagram is consistent with the previous models of the Library Reservation System.

The identified differences clarify the software architecture and do not contradict the existing requirements, data model, interaction scenarios, or business process.