# AirBnB Clone - The Console

Welcome to the **AirBnB Clone - The Console** project! This repository contains the first phase of a four-phase project to develop a complete AirBnB clone. In this phase, we implement the command-line interface (CLI), referred to as "The Console," which serves as the backbone of the application.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Usage](#usage)
- [Commands](#commands)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Examples](#examples)
- [Authors](#authors)
- [License](#license)

## Description

The **AirBnB Clone - The Console** is a command-line tool that allows users to manage the application's data models. This includes creating, updating, retrieving, and deleting objects (e.g., `User`, `Place`, `State`, `City`, `Amenity`, and `Review`). The console serves as the interface between the user and the storage system, providing commands to interact with the application's back-end data storage.

## Features

- Interactive and non-interactive modes.
- Data persistence using a JSON-based storage system.
- CRUD operations for multiple models (`User`, `Place`, `State`, `City`, `Amenity`, `Review`).
- Object serialization and deserialization.
- Command-line auto-completion for improved usability.

## Usage

The console can operate in two modes:

1. **Interactive Mode**: Runs the console in a shell-like environment, where commands are entered line-by-line.
2. **Non-Interactive Mode**: Executes commands from a script or command pipeline.

### Launching the Console

Run the following command to start the console in interactive mode:

```bash
./console.py
```

To execute a command in non-interactive mode:

```bash
echo "<command>" | ./console.py
```

## Commands

| Command         | Description                                                                         | Example                                  |
| --------------- | ----------------------------------------------------------------------------------- | ---------------------------------------- |
| `create`        | Creates a new instance of a model and saves it to the storage.                      | `create User`                            |
| `show`          | Displays the details of a specific instance based on its class and ID.              | `show User 1234-5678-9012`               |
| `destroy`       | Deletes a specific instance based on its class and ID.                              | `destroy User 1234-5678-9012`            |
| `all`           | Displays all instances of a specific class or all classes if no class is specified. | `all User` or `all`                      |
| `update`        | Updates attributes of a specific instance.                                          | `update User 1234-5678-9012 name "John"` |
| `quit` or `EOF` | Exits the console.                                                                  | `quit`                                   |

Use `help` followed by a command to see detailed instructions:

```bash
help <command>
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/walid-mehelba/AirBnB_clone.git
   ```
2. Navigate to the project directory:
   ```bash
   cd AirBnB_clone
   ```
3. Ensure Python 3.x is installed on your system.

## Project Structure

```
AirBnB_clone/
├── console.py          # Entry point for the console application
├── models/             # Directory containing all data models
│   ├── base_model.py   # BaseModel class (parent of all models)
│   ├── user.py         # User model
│   ├── place.py        # Place model
│   ├── state.py        # State model
│   ├── city.py         # City model
│   ├── amenity.py      # Amenity model
│   ├── review.py       # Review model
│   └── __init__.py     # Package initialization file
├── models/engine/      # Storage engine for data persistence
│   ├── file_storage.py # FileStorage class for JSON-based persistence
│   └── __init__.py     # Package initialization file
├── tests/              # Unit tests for the application
│   ├── test_models/    # Unit tests for models
│   ├── test_engine/    # Unit tests for the storage engine
│   └── ...
└── README.md           # Project documentation
```

## Examples

### Interactive Mode

```bash
$ ./console.py
(hbnb) create User
1234-5678-9012
(hbnb) show User 1234-5678-9012
[User] (1234-5678-9012) {'id': '1234-5678-9012', 'created_at': ..., 'updated_at': ...}
(hbnb) quit
```

### Non-Interactive Mode

```bash
$ echo "create User" | ./console.py
1234-5678-9012
$ echo "show User 1234-5678-9012" | ./console.py
[User] (1234-5678-9012) {'id': '1234-5678-9012', 'created_at': ..., 'updated_at': ...}
```

## Authors

- [Walid Mehelba](https://github.com/walid-mehelba)
