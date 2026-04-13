FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS base
WORKDIR /app
EXPOSE 8080

FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
ARG BUILD_CONFIGURATION=Release
WORKDIR /src
COPY . ./
RUN dotnet restore "GreenStack.Umbraco.UmBootstrap/GreenStack.Umbraco.UmBootstrap.csproj" --locked-mode
RUN dotnet build "GreenStack.Umbraco.UmBootstrap/GreenStack.Umbraco.UmBootstrap.csproj" -c $BUILD_CONFIGURATION --no-restore

FROM build AS publish
RUN dotnet publish "GreenStack.Umbraco.UmBootstrap/GreenStack.Umbraco.UmBootstrap.csproj" -c $BUILD_CONFIGURATION -o /app/publish /p:UseAppHost=false --no-build

FROM base AS final

WORKDIR /app
COPY --chown=1000:1000 --from=publish /app/publish .

RUN mkdir -p keys umbraco/Logs umbraco/Data wwwroot/media \
    && chown -R 1000:1000 keys umbraco wwwroot

USER 1000:1000
ENTRYPOINT ["dotnet", "GreenStack.Umbraco.UmBootstrap.dll", "--console-logger-format=json"]
