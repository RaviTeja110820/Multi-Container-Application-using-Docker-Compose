
FROM mcr.microsoft.com/dotnet/sdk:7.0 as build

WORKDIR /App

COPY . ./

#RUN dotnet restore / publish -c release -o out

RUN dotnet publish -c release -o out


# app image
FROM mcr.microsoft.com/dotnet/runtime:7.0
WORKDIR /app
COPY --from=build /App/out .
ENTRYPOINT ["dotnet", "Worker.dll"]
