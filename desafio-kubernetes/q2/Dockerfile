#https://docs.docker.com/samples/dotnetcore/

FROM mcr.microsoft.com/dotnet/sdk:5.0 AS build-dotnet-core
WORKDIR /app

COPY *.csproj ./
RUN dotnet restore

COPY . ./
RUN dotnet publish -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:5.0
WORKDIR /app
COPY --from=build-dotnet-core /app/out .
EXPOSE 80
CMD ["dotnet", "ConversaoPeso.Web.dll"]