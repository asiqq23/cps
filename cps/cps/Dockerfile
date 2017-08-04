FROM microsoft/dotnet:1.1-sdk
WORKDIR /home/hackathon/cps/cps/cps

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out

ENV ASPNETCORE_URLS http://*:5001
EXPOSE 5001

ENTRYPOINT ["dotnet", "out/cps.dll"]
