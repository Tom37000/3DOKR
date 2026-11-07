FROM mcr.microsoft.com/dotnet/sdk:7.0-alpine AS build

WORKDIR /src

COPY Worker.csproj .

RUN dotnet restore

COPY . .

RUN dotnet publish -c release --self-contained false --no-restore -o /app

FROM mcr.microsoft.com/dotnet/runtime:7.0-alpine

WORKDIR /app

RUN adduser -D supinfo

USER supinfo

COPY --from=build --chown=supinfo:supinfo /app .

CMD ["dotnet", "Worker.dll"]