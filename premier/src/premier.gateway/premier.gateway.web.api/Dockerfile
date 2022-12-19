FROM nspdemo.azurecr.io/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM nspdemo.azurecr.io/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["premier.gateway.web.api/premier.gateway.web.api.csproj", "premier.gateway.web.api/"]
RUN dotnet restore "premier.gateway.web.api/premier.gateway.web.api.csproj"
COPY . .
WORKDIR "/src/premier.gateway.web.api"
RUN dotnet build "premier.gateway.web.api.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "premier.gateway.web.api.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "premier.gateway.web.api.dll"]
