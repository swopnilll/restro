# Setting Up a New Web API Project with .NET CLI

This guide outlines the steps to create and set up a new Web API project using the .NET CLI. Follow these instructions to ensure consistency and proper configuration of your project.

---

## Prerequisites

- **.NET SDK**: Ensure the .NET SDK is installed on your system.
- **IDE**: Use Visual Studio or Visual Studio Code for development. 
- **Terminal Access**: A terminal (command prompt, PowerShell, or any shell) is required to execute .NET CLI commands.

---

## Steps to Create a Web API Project

### 1. Create a New Web API Project

1. Navigate to the folder where you want to create your project. For example:
   ```bash
   cd <path_to_your_folder>
   ```
   Example folder name: `Restaurants`.

2. Use the following command to create a new Web API project:
   ```bash
   dotnet new webapi -n Restaurants.API --no-openapi
   ```
   - `webapi`: Specifies the project template.
   - `-n`: Specifies the project name (e.g., `Restaurants.API`).
   - `--no-openapi`: Excludes OpenAPI (Swagger) support.

3. The command will generate the project structure and files in a folder named `Restaurants.API` within the specified directory.

---

### 2. Create a Solution File

1. Use the following command to create a solution file:
   ```bash
   dotnet new sln -n Restaurants
   ```
   - `sln`: Creates a solution file.
   - `-n`: Specifies the solution name (e.g., `Restaurants`).

2. This creates a `Restaurants.sln` file in your current directory.

---

### 3. Add the Web API Project to the Solution

1. Use the following command to add the Web API project to the solution:
   ```bash
   dotnet sln add Restaurants.API/Restaurants.API.csproj
   ```
   - `sln add`: Adds a project to the solution file.
   - Specify the relative path to the `.csproj` file.

2. After running the command, the solution file will include the Web API project.

---

### 4. Open the Project in an IDE

- Open the folder in Visual Studio or Visual Studio Code.
- If using Visual Studio:
  - Double-click the `Restaurants.sln` file to load the solution.

---

### 5. Run the Web API Project

1. Start the application by clicking the **Run** or **Play** button in your IDE (e.g., Visual Studio).
2. The default browser will open to a URL similar to:
   ```
   https://localhost:<port>/weatherforecast
   ```
   - Replace `<port>` with the actual port displayed in your terminal or browser.
3. You should see a JSON response similar to this:
   ```json
   [
     {
       "date": "2024-12-16T00:00:00Z",
       "temperatureC": 25,
       "temperatureF": 77,
       "summary": "Mild"
     }
   ]
   ```

> **Note**: Install a JSON viewer extension in your browser for a formatted view.

---

## Startup Files in a New Web API Project

1. **Program.cs**
   - The entry point of the application.
   - Configures the host and middleware pipeline.

2. **Controllers/WeatherForecastController.cs**
   - A default controller with a `GET` endpoint (`/weatherforecast`).

3. **appsettings.json**
   - Stores configuration settings (e.g., connection strings, logging settings).

4. **.csproj File**
   - Contains project configuration, dependencies, and build settings.

---

## Additional Notes

- The default project includes a sample `WeatherForecast` endpoint to test your setup.
- Ports may vary between setups; ensure you check the terminal output for the correct port.
- To add additional dependencies or middleware, modify `Program.cs` and other configuration files as needed.

---

## Commands Summary

| Command                                  | Description                                     |
|------------------------------------------|------------------------------------------------|
| `dotnet new webapi -n <ProjectName>`     | Creates a new Web API project.                 |
| `dotnet new sln -n <SolutionName>`       | Creates a new solution file.                   |
| `dotnet sln add <PathToCsproj>`          | Adds a project to the solution.                |
| `dotnet run`                             | Runs the Web API application.                  |

---

Now you’re ready to start building your Web API!
