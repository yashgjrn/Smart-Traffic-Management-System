# Smart Traffic Management System (C++ Console)

A console-based prototype that simulates traffic management operations at a four-way intersection using **C++ and Object-Oriented Programming (OOP)**. The system supports user registration and login, traffic signal prioritization based on vehicle density and emergencies, traffic violation reporting with challan generation, and emergency incident logging. Records are stored in text files for persistence between program runs.

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [System Design](#system-design)
- [Data Persistence](#data-persistence)
- [Getting Started](#getting-started)
- [How to Use](#how-to-use)
- [Files Generated at Runtime](#files-generated-at-runtime)
- [Notes and Assumptions](#notes-and-assumptions)
- [Future Enhancements](#future-enhancements)
- [Credits](#credits)

---

## Overview

The Smart Traffic Management System is a menu-driven C++ application designed to demonstrate how basic traffic operations can be simulated using object-oriented programming and file handling.

The application models a four-way intersection with traffic coming from the North, East, South, and West directions. It processes vehicle density information, prioritizes emergency situations, records traffic violations, generates challan identifiers, and maintains emergency incident records.

The project demonstrates the use of classes, encapsulation, modular program design, conditional logic, file input/output, and persistent data storage without requiring a database.

## Key Features

### 1. User Authentication

- Supports user registration and login.
- Stores user credentials in a local text file.
- Provides a basic authentication mechanism for accessing the application's functionality.

### 2. Smart Traffic Signal Control

- Accepts vehicle counts for all four directions.
- Considers emergency conditions when determining signal priority.
- Prioritizes emergency-affected directions over ordinary traffic.
- Uses vehicle density to determine priority when emergency conditions are absent.
- Records traffic control sessions and signal timing information in a log file.

### 3. Traffic Violation Reporting and Challan Generation

- Allows users to report predefined traffic violations, such as overspeeding and riding without a helmet.
- Applies predefined penalties based on the selected violation.
- Generates unique challan identifiers using a persistent counter.
- Stores violation details, challan identifiers, and penalties in a text file.

### 4. Emergency Incident Reporting

- Records emergency incidents such as accidents, bridge collapses, fallen trees or poles, and waterlogging.
- Stores incident details, including the type of emergency and its location.
- Supports retrieving and filtering recorded incidents by type or location.

### 5. File-Based Data Persistence

- Uses plain text files to store application records.
- Maintains user data, traffic control logs, violation reports, challan counters, and emergency records.
- Preserves stored information between program executions without requiring an external database.

---

## System Design

The application follows a modular, object-oriented design organized around four primary classes.

| Class | Responsibility |
|---|---|
| `User` | Handles user registration and login. |
| `TrafficControl` | Processes vehicle density and emergency priority, determines signal order and timing, and records traffic control sessions. |
| `Violation` | Records traffic violations, applies predefined penalties, and generates challan identifiers. |
| `Emergency` | Records emergency incidents and supports retrieval based on incident type or location. |

### OOP Principles Used

**Encapsulation:** Classes organize related data and operations behind their interfaces.

**Abstraction:** The application exposes high-level operations through its menu-driven interface, keeping the user separate from the internal implementation details.

**Modularity:** Different classes handle separate responsibilities, making the program easier to understand, maintain, and extend.

Inheritance and polymorphism are potential areas for future development.

---

## Data Persistence

The system uses text files instead of a database. The following files are used to store application data.

| File | Purpose |
|---|---|
| `users.txt` | Stores registered user credentials. |
| `signal_log.txt` | Records traffic control sessions and associated signal information. |
| `challan_id.txt` | Maintains the counter used for generating challan identifiers. |
| `violations.txt` | Stores reported traffic violations, challan identifiers, and penalties. |
| `emergencies.txt` | Stores emergency incident details, including type and location. |

The application reads from and writes to these files as required by its operations.

**Note:** Keep the data files in the appropriate working directory. If a file is missing, the program's behavior depends on how that file is handled in the implementation.

---

## Getting Started

### Prerequisites

- A C++17-compatible compiler, such as GCC, Clang, or Microsoft Visual C++.
- A terminal or command prompt.
- Git, if you want to clone the repository.

### Clone the Repository

```bash
git clone https://github.com/yashgjrn/Smart-Traffic-Management-System.git
cd Smart-Traffic-Management-System
```

### Build the Project

If you are using GCC or Clang, compile the source file with:

```bash
g++ -std=c++17 -O2 traffic_system.cpp -o traffic_system
```

This command creates an executable named `traffic_system`.

### Run the Application

**macOS or Linux:**

```bash
./traffic_system
```

**Windows:**

If you compiled the program using GCC on Windows:

```bash
traffic_system.exe
```

Alternatively, you can run the existing executable if it is compatible with your operating system.

---

## How to Use

After launching the application, follow the menu displayed in the terminal.

A typical workflow is:

1. Register a user account if required.
2. Log in using the registered credentials.
3. Select the traffic control functionality to enter vehicle counts and emergency conditions for the four directions.
4. Use the violation reporting functionality to record traffic violations and generate challans.
5. Use the emergency reporting functionality to record incidents and retrieve relevant records.
6. Exit the application when finished.

The exact menu options and navigation depend on the implementation in `traffic_system.cpp`.

---

## Files Generated at Runtime

The program uses local text files to maintain records. Depending on the operations performed, these files may be created or updated during execution.

- `users.txt`
- `signal_log.txt`
- `challan_id.txt`
- `violations.txt`
- `emergencies.txt`

Keep these files in the directory expected by the application. Deleting or modifying them may remove stored records or affect the continuity of challan numbering.

---

## Notes and Assumptions

- This project is a console-based simulation intended for learning and demonstration purposes.
- Traffic signal decisions are based on predefined program logic and user-provided vehicle counts and emergency conditions.
- Challan penalties are predefined within the application and do not necessarily represent current statutory fines.
- Data is stored locally in text files rather than in a centralized database.
- User credentials are stored in a local text file. This is suitable only for a basic demonstration and is not a secure authentication implementation.
- The system does not directly connect to real traffic signals, cameras, vehicle sensors, emergency services, or government databases.
- The application must be compiled for the target operating system if the provided executable is incompatible.

---

## Future Enhancements

Possible improvements include:

- Integrating real-time vehicle detection using cameras or sensors.
- Developing a graphical user interface or web-based dashboard.
- Introducing database storage for more structured and scalable data management.
- Implementing password hashing and stronger authentication.
- Adding configurable signal timing and more advanced traffic optimization algorithms.
- Supporting multiple intersections and coordination between traffic signals.
- Generating downloadable challan reports and traffic analytics.
- Adding unit tests, input validation, and more comprehensive error handling.

---

## Credits

Developed as a C++ project to explore object-oriented programming, traffic management logic, and file-based data persistence.

