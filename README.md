# MyWebApi - ASP.NET Core Web API Project

## Project Overview
This project is a simple ASP.NET Core Web API that demonstrates basic web application functionality and modern DevOps practices. It serves as a practical example of implementing, testing, containerizing, and deploying a web API using CI/CD pipelines. The project was made for LOG430 - Architecture logicielle from École de technologie supérieure.

## Learning Objectives
- Understanding ASP.NET Core Web API development
- Implementing CI/CD with GitHub Actions
- Working with minimal API endpoints
- Building and publishing Docker images
- Understanding HTTP response codes and content

## Technical Stack
- .NET 8.0
- ASP.NET Core Web API
- GitHub Actions for CI/CD
- Docker for containerization
- CSharpier for linting

## Project Structure
```
MyWebApi/
├── MyWebApi/                # Main Web API project
│   ├── Program.cs           # Application entry point
│   └── appsettings.json     # Application configuration
├── .github/
│   └── workflows/
│       └── pipelineConfig.yaml # GitHub Actions workflow for CI/CD
└── Dockerfile               # Dockerfile for building the API image
```

## Getting Started

### Prerequisites
- .NET 8.0 SDK (for local development)
- Docker (for containerization)
- An IDE (Visual Studio, VS Code, or Rider)

### Installation
1. Clone the repository:
   ```bash
   git clone [https://github.com/Reinemaker/LOG430_02_Laboratoire]
   cd LOG430_02_Laboratoire
   ```

2. Restore dependencies:
   ```bash
   dotnet restore MyWebApi
   ```

3. Build the solution:
   ```bash
   dotnet build MyWebApi
   ```

### Running the Application Locally
To run the web API locally:
```bash
cd MyWebApi
 dotnet run
```
The API will be available at `http://localhost:5104`

### Running with Docker
To build and run the API in a Docker container:
```bash
docker build -t mywebapi -f MyWebApi/Dockerfile .
docker run -d -p 8080:8080 --name mywebapi-container mywebapi
```
The API will be available at `http://localhost:8080`

## CI/CD Pipeline
This project uses GitHub Actions for continuous integration and deployment. The workflow includes:
- **Linting:** Checks code style using CSharpier
- **Build:** Builds the project
- **Unit Tests:** (If present) Runs unit tests
- **Docker Build & Publish:** Builds and pushes the Docker image to Docker Hub

The workflow file is located at `.github/workflows/pipelineConfig.yaml`.

### Docker Hub Publication
The pipeline will automatically build and push the Docker image to Docker Hub when changes are pushed to the `main` branch. Ensure you have set the following secrets in your GitHub repository:
- `DOCKERHUB_USERNAME`
- `DOCKERHUB_PASSWORD`

## API Endpoints

### GET /
- **Description:** Returns a "Hello World!" message
- **Response:** 200 OK with "Hello World!" content

## Future Improvements
- Add more endpoints
- Implement authentication
- Add database integration
- Enhance test coverage

## Author
Minjae Lee [LEEM29379701]

## License
This project is created for educational purposes.

## Acknowledgments
- ASP.NET Core documentation
- GitHub Actions documentation
- Docker documentation
- CSharpier