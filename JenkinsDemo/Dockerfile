FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app
COPY *.csproj .
RUN dotnet restore
COPY . ./
RUN dotnet publish --no-restore -c Release -o out



FROM mcr.microsoft.com/dotnet/sdk:8.0AS final
WORKDIR /app
COPY --from=base /app/out .
ENTRYPOINT ["dotnet", "JenkinsDemo.dll"]

