FROM mcr.microsoft.com/dotnet/core/sdk:3.1

## Creating WorkDir for Docker Container environment
WORKDIR /app


COPY *.sln .

## Copy the project files
COPY TestApi/*.csproj ./TestApi/

## restore dependencies
RUN dotnet restore

## Copy files
COPY . ./TestApi/

## Setting workdir
WORKDIR /app/TestApi/

## publish the app
RUN dotnet publish -c Release -o out

## Exposing the container ports
EXPOSE 5001
EXPOSE 5000

ENTRYPOINT ["dotnet", "TestApi/bin/Release/netcoreapp3.1/TestApi.dll"]