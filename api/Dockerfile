#.Net Core Web API
FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build-env
WORKDIR /app/api
## copy csproj file first
COPY api.csproj ./
RUN dotnet restore
## copy rest of the files
COPY . ./
RUN dotnet publish -c Release -o out
## aspnet so we don't get the whole sdk
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS aspnet
WORKDIR /app/api
EXPOSE 80
COPY --from=build-env /app/api/out .
ENTRYPOINT ["dotnet", "api.dll"]