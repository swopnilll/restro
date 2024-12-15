# Restaurant API Project

## Overview
This is a basic Web API project built using .NET 8. It serves as an introductory example to understand the structure, configuration, and functionality of a Web API application.

## Project Structure

### Project File (`RestaurantAPI.csproj`)
- **Purpose**: Contains the basic settings for the project.
- **Key Configurations**:
  - **.NET Framework Version**: Targets .NET 8.
  - **Nullable Reference Types**: Enabled.
  - **Implicit Usings**: Enabled.
  - **Invariant Globalization**: (Optional) Removed due to potential compatibility issues with some libraries.
  - **Dependencies**: External packages like Entity Framework or logging packages will be added here in the future.

### Properties Folder
- **`launchSettings.json`**:
  - **Purpose**: Defines launch settings for running the API locally.
  - **Profiles**: Options include HTTPS, HTTP, IIS Express, and WSL.
  - **Key Features**:
    - Set ports for HTTP and HTTPS (e.g., `http://localhost:7005` and `http://localhost:5272`).
    - Option to launch the browser automatically when running the project.
    - Configure `ASP.NET Core Environment` variable (e.g., `Development`, `Production`).

### `Program.cs`
- **Purpose**: Configures the application startup logic.
- **Key Sections**:
  - **Dependency Injection (DI)**: Registers services (e.g., `AddControllers` for controller support and model binding).
  - **HTTP Request Pipeline**:
    - Middleware setup:
      - `UseHttpsRedirection`: Redirects HTTP to HTTPS.
      - `UseAuthorization`: Enables authorization middleware (not used initially).
      - `MapControllers`: Maps HTTP routes to controller actions.
    - Application is built (`builder.Build()`) and started (`app.Run()`).

### Controller (`WeatherForecastController.cs`)
- **Purpose**: Contains endpoints to handle HTTP requests.
- **Key Components**:
  - **Route Attribute**: Defines the base route for the controller (e.g., `/weatherforecast`).
  - **Action Methods**:
    - Example: `Get()` method returns a list of random weather forecasts.
    - Supports routing customization, e.g., adding prefixes like `/api` or additional paths like `/example`.
  - **Model Binding**: Automatically converts C# objects to JSON responses.

### Model (`WeatherForecast.cs`)
- **Purpose**: Represents the data returned by the API.
- **Properties**:
  - `Date`, `TemperatureC`, `TemperatureF`, `Summary`.

### Configuration Files
- **`appsettings.json` and `appsettings.Development.json`**:
  - **Purpose**: Store configuration details for different environments.
  - **Example Use Cases**:
    - Connection strings for databases.
    - Environment-specific settings.

### HTTP File (`RestaurantAPI.http`)
- **Purpose**: Simplifies testing HTTP requests directly within Visual Studio.
- **Features**:
  - Define variables (e.g., `{{RestaurantAPI_Host}} = http://localhost:5272`).
  - Construct and send HTTP requests (e.g., `GET` request to `/weatherforecast/example`).
  - View responses, headers, and status codes without external tools like Postman.

## How to Run the Project
1. Open the solution in Visual Studio.
2. Select a launch profile from the dropdown (e.g., HTTPS).
3. Run the project (F5).
4. Access the API endpoints via a browser or HTTP client (e.g., `http://localhost:7005/weatherforecast`).

## Customization and Testing
### Routes
- Modify the `[Route]` attribute in the controller to customize endpoint paths.
  - Example: Change `[Route("weatherforecast")]` to `[Route("api/weather")]`.

### Environment Variables
- Set `ASPNETCORE_ENVIRONMENT` in `launchSettings.json` to test different configurations (e.g., `Development`, `Production`).

### HTTP File Usage
1. Open `RestaurantAPI.http` in Visual Studio.
2. Update request paths to match your configuration.
3. Click **Send Request** to execute and test endpoints.

## Summary
This project demonstrates the foundational structure and features of a Web API in .NET 8, including:
- Dependency Injection
- Routing and Model Binding
- Middleware Configuration
- Environment-Specific Settings
- Built-in API testing tools (HTTP files).

Further enhancements will include adding external libraries, connecting to a database, and implementing authentication and authorization.
