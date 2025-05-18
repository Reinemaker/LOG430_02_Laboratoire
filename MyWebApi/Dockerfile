FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app
EXPOSE 80

# Copy everything
COPY . ./

# Restore as distinct layers
RUN dotnet restore --no-cache

# Build the application
RUN dotnet publish -c Release -o out

# Copy the output
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app/out ./

ENTRYPOINT ["dotnet", "MyWebApi.dll"]