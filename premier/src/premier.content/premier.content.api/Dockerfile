#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM nspdemo.azurecr.io/dotnet/aspnet:7.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM nspdemo.azurecr.io/dotnet/sdk:7.0 AS build
WORKDIR /src
COPY ["premier.content.api/premier.content.api.csproj", "premier.content.api/"]
RUN dotnet restore "premier.content.api/premier.content.api.csproj"
COPY . .
WORKDIR "/src/premier.content.api"
RUN dotnet build "premier.content.api.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "premier.content.api.csproj" -c Release -o /app/publish /p:UseAppHost=false

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "premier.content.api.dll"]
