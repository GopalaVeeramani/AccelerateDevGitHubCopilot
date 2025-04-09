# Library App

## Description
The **Library App** is a console-based library management system built with .NET 8.0. It allows users to manage patrons, books, and loans. The application follows a clean architecture approach, separating concerns between the core business logic, infrastructure, and user interface layers.

## Project Structure
- `src/`
  - `Library.ApplicationCore/`
    - `Entities/` - Contains domain entities like `Patron`, `Loan`, `Book`, and `Author`.
    - `Enums/` - Defines enums for statuses like `MembershipRenewalStatus` and `LoanReturnStatus`.
    - `Interfaces/` - Declares repository and service interfaces.
    - `Services/` - Implements business logic services like `PatronService` and `LoanService`.
    - `Library.ApplicationCore.csproj` - Project file for the core library.
  - `Library.Console/`
    - `appSettings.json` - Configuration file for JSON paths.
    - `CommonActions.cs` - Defines common user actions in the console app.
    - `ConsoleApp.cs` - Main entry point for the console application.
    - `ConsoleState.cs` - Enum for managing application states.
    - `Json/` - Contains sample JSON data files for authors, books, patrons, and loans.
    - `Program.cs` - Initializes and runs the console application.
    - `Library.Console.csproj` - Project file for the console application.
  - `Library.Infrastructure/`
    - `Data/` - Implements data access using JSON files.
      - `JsonData.cs` - Handles loading, saving, and populating JSON data.
      - `JsonPatronRepository.cs` - Repository for managing patron data.
      - `JsonLoanRepository.cs` - Repository for managing loan data.
    - `Library.Infrastructure.csproj` - Project file for the infrastructure library.
- `tests/`
  - `UnitTests/` - Contains unit tests for core services and functionality.
    - `LoanFactory.cs` - Helper class for creating test data.
    - Other test files for `PatronService` and `LoanService`.

## Key Classes and Interfaces
### Core Classes and Interfaces
- `Library.ApplicationCore/Entities/`
  - `Patron` - Represents a library patron.
  - `Loan` - Represents a loan of a book item.
  - `Book` - Represents a book in the library.
  - `Author` - Represents an author of a book.
- `Library.ApplicationCore/Interfaces/`
  - `IPatronRepository` - Interface for patron data access.
  - `ILoanRepository` - Interface for loan data access.
  - `IPatronService` - Interface for patron-related business logic.
  - `ILoanService` - Interface for loan-related business logic.
- `Library.ApplicationCore/Services/`
  - `PatronService` - Handles membership renewal logic.
  - `LoanService` - Manages loan extensions and returns.

### Infrastructure Classes
- `Library.Infrastructure/Data/`
  - `JsonData` - Handles loading, saving, and populating data from JSON files.
  - `JsonPatronRepository` - Implements `IPatronRepository` using JSON data.
  - `JsonLoanRepository` - Implements `ILoanRepository` using JSON data.

### Console Application
- `Library.Console/`
  - `ConsoleApp` - Main class for the console application, managing user interactions and state transitions.
  - `CommonActions` - Enum for user actions like searching patrons or extending loans.
  - `ConsoleState` - Enum for application states like `PatronSearch` and `LoanDetails`.

## Usage
### Prerequisites
- .NET 8.0 SDK installed on your machine.

### Running the Application
1. Clone the repository:
   ```sh
   git clone <repository-url>
   cd LibraryApp
