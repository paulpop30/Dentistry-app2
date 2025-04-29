
# 🦷 Dentistry-app2 – Dental Clinic Management System

**Dentistry-app2** is a modular, object-oriented Java application designed to simulate and manage the core operations of a dental clinic. It enables efficient handling of patient data, appointment scheduling, and clinical reports. The app supports multiple persistence layers (in-memory, file-based, and database-backed using JDBC), and offers robust data validation and reporting via Java 8 Streams. Built with clean architecture and layered design principles, this project is ideal for showcasing your understanding of scalable Java development.

---

## 🚀 Features

- Register, update, and delete patients and appointments
- Track appointment status and filter by date, patient, or issue
- Generate dynamic reports using Java Streams
- Switch between in-memory, file-based, or database storage via configuration
- Input validation for business rules (e.g. valid dates, phone numbers)
- Console-based UI for easy interaction

---

## 🏗️ Architecture Overview

Dentistry-app2 follows a **Layered Architecture** consisting of:

### 1. 📦 Domain Layer (`domain/`)
Defines the core business entities and validation logic.

- `Identifiable.java` – Interface with an `id` field
- `Patient.java` – Represents a patient with fields: `id`, `name`, `phoneNumber`
- `Appointment.java` – Represents a clinic appointment with fields: `id`, `patient`, `problem`, `date`, `status`

---

### 2. 💾 Repository Layer (`repository/`)
Handles data persistence and storage abstraction.

- Repositories handle data storage and retrieval. The system includes several repository types:

- MemoryRepository: In-memory repository for storing entities.

- AppointmentRepository, PatientRepository: Specialization of the Repository class for appointments and patients.

- AppointmentTextRepository, AppointmentBinaryRepository, AppointmentDBRepository: Different types of data persistence for appointments.

- FilterRepository: A repository responsible for filtering entities based on specific criteria.
  
**Configurable via `settings.properties`:**
```properties
Repository = database
Location = data
Patients = patients
Appointments = appointments
```

---

### 3. ⚙️ Service Layer (`service/`)
Implements business logic and operations on domain entities.

- `PatientService`  
  - Add/update/remove patients  
  - Search/filter patients by name or ID  
  - Generate patient-based reports

- `AppointmentService`  
  - Schedule or cancel appointments  
  - Track and update appointment statuses  
  - Generate reports using Java Streams:
    - Filter appointments by date
    - Count appointments per patient
    - Identify most common problems
 - `FilterService`:
   - Provides filtered data based on repository data.
---

### 4. 🖥️ UI Layer (`ui/`)
Console-based interface and entry point for the application.

- `Main.java` – Entry point: loads settings, initializes repositories and services
- `UI.java` – Displays a text-based menu to:
  - Manage patients and appointments
  - Display filtered results and reports
  - Provide feedback to the user

---

## 📊 Java Streams-Based Reporting

Leverages Java 8 Streams for powerful data querying:
- List all appointments by patient
- Get contact info by patient ID
- Identify common treatment problems
- Find appointments by status/date
- Detect which patients need follow-up

---

## 🛠 Technologies Used

- **Java 8+**
- **JDBC** for database communication
- **File I/O** for plaintext data persistence
- **Java Streams** for modern data processing
- **Properties files** for dynamic configuration
- **Design Patterns**:
  - Factory Pattern (`RepositoryFactory`)
  - Layered Architecture (separates UI, business logic, and data layers)

---

# Project Title

## Description
This project is a dental appointment management system. It allows the management of patient data, appointments, and filtering of records. It includes a service layer for business logic and a UI for interaction with the system.

## File Structure

```
├── Domain
│   ├── Appointment.java        # Represents a dental appointment.
│   └── Patient.java           # Represents a patient in the system.
├── Repository
│   ├── AppointmentRepository.java  # Repository for managing appointments.
│   ├── PatientRepository.java     # Repository for managing patient data.
│   ├── FilterRepository.java     # Repository for filtering entities based on criteria.
│   └── MemoryRepository.java     # In-memory repository for storing entities.
├── Service
│   ├── AppointmentService.java   # Service layer for managing appointments.
│   ├── PatientService.java      # Service layer for managing patients.
│   ├── FilterService.java       # Service layer for filtered data.
│   └── IService.java            # Interface for basic CRUD operations.
├── UI
│   ├── IUi.java                 # Interface for UI operations.
│   └── MainUi.java              # Main UI for interacting with the system.
├── MyExceptions
│   └── EmptyRepoException.java  # Custom exception for handling empty repositories.
└── Main.java                    # Main entry point of the system.
```

## Requirements
- Java 8 or higher
- An IDE such as IntelliJ IDEA or Eclipse

## Installation
Clone the repository and open it in your preferred IDE.

## Usage
Run the `Main.java` file to start the system. Follow the on-screen instructions to manage appointments and patients.

## License
This project is licensed under the MIT License.


## 🧪 How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/paulpop30/Dentistry-app2.git
cd Dentistry-app2
```

### 2. Configure Repository Type

Edit the `settings.properties` file to select storage type:
```properties
Repository = database   # or "file" or "memory"
```

### 3. Compile and Run
```bash
javac -d bin */*.java
java -cp bin ui.Main
```

---
