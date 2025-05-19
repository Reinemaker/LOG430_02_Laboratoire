FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /app

# Copy csproj and restore dependencies
COPY MyWebApi/*.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY MyWebApi/ ./
RUN dotnet publish MyWebApi.csproj -c Release -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/aspnet:8.0
WORKDIR /app
COPY --from=build /app/out .
EXPOSE 80
EXPOSE 443

ENTRYPOINT ["dotnet", "MyWebApi.dll"]