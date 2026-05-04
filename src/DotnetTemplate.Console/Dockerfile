FROM mcr.microsoft.com/dotnet/sdk:10.0@sha256:8a90a473da5205a16979de99d2fc20975e922c68304f5c79d564e666dc3982fc AS build
WORKDIR /App

# Copy everything
COPY . ./
# Restore as distinct layers
RUN dotnet restore
# Build and publish a release
RUN dotnet publish -o out

# Build runtime image
FROM mcr.microsoft.com/dotnet/runtime:10.0@sha256:8fb7ff015fcf0ebc6e90105bd6db06875954e6dc3d374b9dbb34c732867d13e4
WORKDIR /App
COPY --from=build /App/out .
ENTRYPOINT ["dotnet", "DotnetTemplate.Console.dll"]