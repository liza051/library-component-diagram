# Defense — Library Reservation System Component Diagram

## 1. Intent and Acceptance Criteria

The purpose of this laboratory work is to describe the software architecture of the Library Reservation System using a UML Component Diagram. The diagram represents the main system components, their interfaces, dependencies, and external integrations.

The model is considered complete if it shows the system boundary, component responsibilities, provided and required interfaces, dependencies, and the external email provider.

## 2. Main Components

The component diagram includes the following elements:

- **User Interface** — provides interaction for Readers and Librarians.
- **API / Backend** — receives and processes client requests.
- **Catalog Service** — manages book catalog information.
- **Reservation Service** — handles book copy reservations.
- **Loan Service** — manages book loans and returns.
- **Notification Service** — handles notification requests.
- **Data Access Layer** — provides access to stored information.
- **Library Database** — stores system data.
- **External Email Provider** — delivers email notifications outside the system boundary.

## 3. Top-3 Discrepancies and Resolutions

1. **Data entities and software components:** The previous ER model describes data entities, while the component diagram describes software modules. The Data Access Layer and Library Database clarify how system components access and store data.

2. **Reservation logic distribution:** The reservation process requires both request handling and business logic. The API / Backend handles incoming requests, while the Reservation Service manages reservation operations.

3. **Notification delivery:** The notification process requires an external delivery mechanism. The Notification Service uses the Email Delivery Interface provided by the External Email Provider.

## 4. Consistency with Previous Laboratory Work

The component diagram is consistent with the previous laboratory models:

- Lab 1 — Domain and Data Model (ER).
- Lab 2 — Use Case Diagram and scenarios.
- Lab 3 — Sequence Diagrams.
- Lab 4 — Activity Diagram.

The component structure supports the previously described book reservation process.

## 5. Final Result

The UML Component Diagram describes the main architectural structure of the Library Reservation System, its internal components, interfaces, dependencies, and external email integration.

The model and its documentation were reviewed for consistency with the project requirements and previous laboratory work