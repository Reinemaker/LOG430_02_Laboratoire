# MyWebApi - ASP.NET Core Web API Project

## Project Overview
This project is a simple ASP.NET Core Web API that demonstrates basic web application functionality and testing practices. It serves as a practical example of implementing and testing a web API using modern development practices.

## Learning Objectives
- Understanding ASP.NET Core Web API development
- Implementing unit and integration tests
- Working with minimal API endpoints
- Understanding HTTP response codes and content

## Technical Stack
- .NET 8.0
- ASP.NET Core Web API
- xUnit for testing
- Microsoft.AspNetCore.Mvc.Testing for integration tests

## Project Structure
```
MyWebApi/
├── MyWebApi/                 # Main Web API project
│   ├── Program.cs           # Application entry point
│   └── appsettings.json     # Application configuration
└── MyWebApi.Tests/          # Test project
    └── HomepageTest.cs      # Integration tests
```

## Getting Started

### Prerequisites
- .NET 8.0 SDK
- An IDE (Visual Studio, VS Code, or Rider)

### Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/Reinemaker/LOG430_02_Laboratoire]
   cd MyWebApi
   ```

2. Restore dependencies:
   ```bash
   dotnet restore
   ```

3. Build the solution:
   ```bash
   dotnet build
   ```

### Running the Application
To run the web API:
```bash
cd MyWebApi
dotnet run
```
The API will be available at `http://localhost:5104`

### Running Tests
To run the tests:
```bash
dotnet test
```

## API Endpoints

### GET /
- **Description:** Returns a "Hello World!" message
- **Response:** 200 OK with "Hello World!" content
- **Test Coverage:** Verified through integration tests

## Testing Strategy
The project includes integration tests that verify:
1. The homepage returns "Hello World!"
2. The homepage returns a 200 OK status code

Tests are implemented using xUnit and Microsoft.AspNetCore.Mvc.Testing for integration testing.

## Future Improvements
- Add more endpoints
- Implement authentication
- Add database integration
- Enhance test coverage

## Author
Minjae Lee

## License
This project is created for educational purposes.

## Acknowledgments
- ASP.NET Core documentation
- xUnit testing framework
- Microsoft.AspNetCore.Mvc.Testing