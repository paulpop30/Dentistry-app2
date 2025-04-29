### Dentistry application

🔧 General Purpose
Dentistry-app2 is a Java-based management system for a dental clinic. It handles core features such as:

Patient management

Appointment scheduling and tracking

Treatment details

Data persistence via file or database repositories

Report generation using Java Streams

The app is console-based and organized using object-oriented design and layered architecture (domain, repository, service, UI).

📁 Code Structure and Main Components
1. Domain Layer (domain/)
This defines the core entities and business logic.

Patient.java
Represents a patient with fields like ID, name, and phone number.

Appointment.java
Represents an appointment with fields like patient, problem description, date, and status.

Validator.java / PatientValidator.java / AppointmentValidator.java
Validate that patients and appointments meet business rules (e.g., non-empty names, valid dates).

  - Implement classes in the repository that allow storing and retrieving data to/from a relational database. The decision of which repositories are employed, as well as the location of the 
  repository input files / database will be made available via the program’s settings.properties file and the Java Properties class. See an example is below:
  - Repository = database
  - Location = data
  - Patients = patients
  - Appointments = appointments

- Provide various reports, using Java 8 streams. You should create at least 5 different reports. See some examples below:
  - all the appointments for a certain patient (and their status); 
  -	the problems of a certain patient; 
  -	the phone number of a certain patient (given by id); 
  -	the name of the persons who booked a certain car; 
  -	all cars rented by a certain person; 
  -	the list of birthday cakes that for ordered for a given day; 
  -	the days when a certain birthday cake has to be delivered.
