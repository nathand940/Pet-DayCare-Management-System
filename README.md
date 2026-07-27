## Pet DayCare Management System (Java, OOP, MVC, XML Persistence)

A modular, object‑oriented Java application designed to manage pets in a daycare environment. The system supports registering pets, updating details, generating reports, calculating weekly fees, and saving/loading data using XML persistence. It demonstrates strong use of inheritance, polymorphism, utility classes, controllers, and clean separation of concerns.

## Features

## Object-Oriented Design

•Abstract superclass Pet
•Subclasses Dog, Cat, and Misc
•Each subclass implements its own calculateWeeklyFee() and toString()
•Shared fields and validation logic inherited from Pet

## Modular Architecture (MVC-inspired)

•models package: Pet, Dog, Cat, Misc
•controllers package: DayCare (main business logic)
•utils package: validation utilities (DogBreedUtility, CatToyUtility, MiscAnimalUtility)
•main package: Driver (user interface)

## CRUD Operations

•Add pets (with type-specific attributes)
•Update pet details
•Delete pets by index or ID
•Retrieve pets by index or ID

## Reporting & Statistics

•List all pets
•List dogs, cats, misc animals
•Dangerous dogs
•Indoor cats
•Pets staying more than X days
•Weekly income calculation
•Average attendance
•Search pets by owner
•Sort pets alphabetically by name

## XML Persistence

•Save full daycare state to daycare.xml
•Load saved data back into the system
•XStream configured with aliases and allowed types

## Tech Stack

•Java (OOP, inheritance, polymorphism)
•XStream XML serialization
•ArrayList for dynamic storage
•ScannerInput & custom utilities for validation
•Bubble sort implementation

## System Overview

## Pet Superclass
Defines shared fields:

•ID
•Name
•Owner
•Sex
•Days per week

Includes:

•Constructor
•Getters/setters with validation
•Abstract calculateWeeklyFee()

## Dog Subclass
Adds:

•Breed
•Dangerous breed flag
•Neutered flag
•Pricing constants
•Fee calculation based on danger status and attendance

## Cat Subclass
Adds:

•Favourite toy
•Indoor cat flag
•Toy validation via CatToyUtility
•Fee calculation with indoor surcharge

## Misc Subclass
Adds:

•Type (validated via MiscAnimalUtility)
•Special care flag
•Fee calculation with special care surcharge

## DayCare Controller
Handles:

•CRUD operations
•Reporting
•Statistics
•Searching
•Sorting
•XML persistence

## Driver (Main Program)
Provides:

•Main menu
•CRUD menu
•Reports menu
•Search & sort features
•Save/load options

How to Run
Compile all Java files:

javac main/Driver.java

Run the program:

java main.Driver

## Known Issues
•XStream produces warnings related to deprecated sun.misc.Unsafe methods.
These do not affect saving/loading functionality.
•checkIn() and checkOut() methods were planned but not implemented due to time constraints.

## What I Learned

•Designing inheritance hierarchies and using super() correctly
•Implementing polymorphism with @Override
•Using utility classes for validation
•Applying ternary operators to simplify logic
•XML persistence and error handling with try/catch
•Structuring a multi‑package Java application
•Separating UI, logic, and models for future scalability

## Future Improvements

•Implement check-in/check-out functionality
•Replace bubble sort with a more efficient algorithm
•Add GUI or web interface
•Improve error handling and input validation
•Expand Misc animals into dedicated subclasses
•Replace XStream with a modern persistence solution (JSON or database)

## Why This Design Supports Future Growth

•New animals (e.g., rabbits, alpacas, ferrets) can be added easily by creating new subclasses of Pet
•The system avoids the “giant class” problem by separating models, controllers, utilities, and UI
•Driver remains simple and mobile‑app‑friendly
•ArrayList allows unlimited pets without hardcoded limits

## References

•W3Schools (super, final, constructors, try/catch, annotations, HashMap, HashSet, switch/case)
•DataCamp (boolean operators)
•Oracle Docs (package imports)
•GeeksForGeeks (ternary operator)
