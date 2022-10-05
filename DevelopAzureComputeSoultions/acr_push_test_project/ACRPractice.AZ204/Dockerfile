# pull dotnet SDK image and tag it as base
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base

# checkout to folder add inside base image
WORKDIR /app

# set container listen to http and https ports
EXPOSE 80
EXPOSE 443

# pull dotnet SDK image and tag it as build
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build

# checkout to folder src
WORKDIR /src

# copy project from current dirctory inside filesystem to the build container
COPY ["ACRPractice.AZ204/ACRPractice.AZ204.csproj", "ACRPractice.AZ204/"]

# restore packages of just copied project file
RUN dotnet restore "ACRPractice.AZ204/ACRPractice.AZ204.csproj"

# copy all contents of the ACRPractice.AZ204 folder to the container
COPY . .

# checkou to the /src/ACRPractice.AZ204
WORKDIR "/src/ACRPractice.AZ204"

# run dotnet build in directory /src/ACRPractice.AZ204
RUN dotnet build "ACRPractice.AZ204.csproj" -c Release -o /app/build

# retag build container as publish
FROM build AS publish

# publish dotnet project with release configuration
RUN dotnet publish "ACRPractice.AZ204.csproj" -c Release -o /app/publish

# retag base base container as final
FROM base AS final

# checkout to folder /app
WORKDIR /app

# copy all files inside folder /app/publish at publish container to the current working directory
COPY --from=publish /app/publish .

# run dotnet application
ENTRYPOINT ["dotnet", "ACRPractice.AZ204.dll"]
