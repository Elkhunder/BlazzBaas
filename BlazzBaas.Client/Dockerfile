FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
USER $APP_UID
WORKDIR /app
EXPOSE 8080
EXPOSE 8081

FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
COPY ["BlazzBaas.Client/BlazzBaas.Client.csproj", "BlazzBaas.Client/"]
RUN dotnet restore "BlazzBaas.Client/BlazzBaas.Client.csproj"
COPY . .
WORKDIR "/src/BlazzBaas.Client"
RUN dotnet build "BlazzBaas.Client.csproj" -c $BUILD_CONFIGURATION -o /app/build

FROM build AS publish
ARG BUILD_CONFIGURATION=Release
RUN dotnet publish "BlazzBaas.Client.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "BlazzBaas.Client.dll"]
