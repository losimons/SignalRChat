Check [Documentation](https://docs.microsoft.com/nl-nl/aspnet/core/tutorials/signalr?tabs=visual-studio-code&view=aspnetcore-2.2) about Web app + Signal R 

# Setup
Create new folder
Go to folder
Run: 

```
dotnet new webapp -o nameOfApp
code -r SignalRChat
```

# Add SignalR Client library
```
dotnet tool install -g Microsoft.Web.LibraryManager.Cli
libman install @aspnet/signalr -p unpkg -d wwwroot/lib/signalr --files dist/browser/signalr.js --files dist/browser/signalr.min.js
```
With the latter, you specify the following things: 
The parameters specify the following options:
- Use the unpkg provider.
- Copy files to the wwwroot/lib/signalr destination.
- Copy only the specified files.

# Create a SignalR Hub
Hub => handles Client-Server Communication
Hub =>  manages connections, groups, and messaging.

SendMessage method can be called by a connected client to send a message to all clients. 
JavaScript client code that calls the method is created later.

# Configure Hub
The SignalR Server must be configured to pass the request to SignalR.
= set up the route url for the request in StartUp.

