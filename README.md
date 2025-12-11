# 🚍 VTS — Vehicle Transit Simulator

*A large-scale object-oriented simulation project built for CSCI 3081W (Program Design & Development)

> **Note:** This repository contains documentation, system design, and media related to VTS.
> The source code cannot be published due to course policy, but this README provides a complete overview of the project’s architecture and my individual contributions.

---

## 📌 Overview

VTS (Vehicle Transit Simulator) is a modular transit simulation engine designed to model buses, trains, routes, passengers, and emissions across a virtual city.
The system emphasizes clean architecture, extensibility, and object-oriented design, using real-world design patterns such as:

Observer (for CO₂ emissions tracking)

Decorator (to dynamically modify vehicle behavior/appearance)

Factory (for generating vehicles and routes)

Strategy (for controlling passenger generation behavior)

The simulator updates in real time, rendering vehicles on a map and displaying route progress, passenger counts, and environmental impact.

---

## 🧱 Core Features
### 🚍 Vehicle Simulation

- Bus and train models with independent movement, update loops, and route logic

- Dynamic passenger loading/unloading

- Configurable speeds, capacities, and routes

### 🌿 CO₂ Emissions Tracking

- Real-time emissions reporting using an Observer pattern

- Dashboard displaying cumulative emissions across all vehicles

- Extensible design for adding additional environmental metrics

### 🎨 Decorator System

- Used to enhance or alter vehicle rendering logic

-Example: TransparentDecorator, which dynamically adjusts alpha values

- Allows adding features without modifying the base Vehicle class

### 🗺 Interactive GUI

- Map-based visualization of routes and vehicle positions

- Real-time simulation playback

- Toggleable overlays (emissions, passenger data, etc.)

### 🧪 Testing & Reliability

- Comprehensive unit tests for vehicle behaviors, decorators, observers, and configuration parsing

- Integration tests for the simulation update loop

### 🧩 System Architecture

- High-Level Component Diagram
flowchart TD
    A[Simulation Engine] --> B[Vehicle System]
    A --> C[Route Manager]
    A --> D[Passenger Generator]

    B --> E[Vehicle Decorators]
    B --> F[CO₂ Observer]

    C --> G[Route Configurations]

    A --> H[Rendering / GUI]

- Class Relationship Diagram (Simplified)
classDiagram{
    class Vehicle {
        +update()
        +move()
        +getAlpha()
    }

    class VehicleDecorator {
        -Vehicle decoratedVehicle
        +update()
        +getAlpha()
    }

    class TransparentDecorator {
        +getAlpha() 155
    }

    class EmissionsObserver {
        +notify()
    }

    Vehicle <|-- Bus
    Vehicle <|-- Train
    Vehicle <|-- VehicleDecorator
    VehicleDecorator <|-- TransparentDecorator
    Vehicle --> EmissionsObserver
    

## 👤 My Contributions

- I played a key role in designing and implementing several core systems within VTS. My primary responsibilities included:

### 🧩 Decorator System

- Implemented the Vehicle Decorator pattern, including the TransparentDecorator

- Ensured decorators could modify rendering logic without altering base classes

- Added tests to guarantee decorator chain correctness

### 🌿 Emissions Tracking

- Built the CO₂ calculation system and integrated it with the simulation loop

- Implemented an Observer that listens to vehicle updates and logs emissions

- Designed the data pipeline for exporting emissions results to the GUI

### 🚂 Vehicle Behaviors

- Developed movement and update logic for vehicles on complex routes

- Implemented constraints such as dwell times, stop detection, and capacity rules

### 🧪 Testing & Debugging

- Wrote unit tests for vehicle updates, decorators, and observer interactions

- Debugged rendering synchronization issues during multi-vehicle updates

### 📐 Documentation

- Authored UML diagrams and internal design documents

- Helped formalize the architectural decomposition used by the entire project team

### 📸 Media

- Since code cannot be shared, here are visual examples of the project:

✔️ Simulation screenshots (routes, vehicles, UI overlays)

✔️ GIF/video of vehicles updating on the map

✔️ Emissions dashboard in action

✔️ Example of a transparent decorator applied

- They can all be found on [pyne.dev](https://pyne.dev)

### 🛠 Tech Stack

- Language: Java, JavaScript

- Build System: Gradle

- Patterns Used: Decorator, Observer, Factory, Strategy

- Testing: GoogleTest

- Visualization: Provided simulation/graphics framework + custom rendering hooks

### 📚 What I Learned

- Through VTS, I strengthened my skills in:

Object-oriented design & architecture

Clean abstractions and extensibility

C++ memory management and inheritance hierarchies

Design patterns applied to real engineering problems

Collaborating in a multi-developer environment

Writing maintainable tests in large systems

### 🚫 Source Code Disclaimer

- This project was completed as part of the CSCI 3081W: Program Design & Development course at the University of Minnesota.
Course policy prohibits publicly sharing source code.
This repository contains only documentation, diagrams, and media relevant to my personal portfolio.

### 🔗 Portfolio

- You can view the accompanying project write-up on my portfolio here:
https://pyne.dev/
