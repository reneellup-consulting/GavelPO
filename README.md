# GavelPoMobile
# GavelPoMobile

GavelPoMobile is a cross-platform mobile application built with .NET MAUI for managing and tracking Purchase Orders. The solution follows Clean Architecture principles, utilizing an ASP.NET Core Web API backend and CQRS pattern for robust and scalable performance.

## 📱 Project Structure

The solution is divided into several key projects to enforce separation of concerns:

### Frontend
* **`GavelPoMobile.Maui`**: The .NET MAUI client application containing the user interface, views, view models, and mobile-specific services. Includes rich UI components (DataGrid, Scheduler, Charts, TabViews) powered by DevExpress.

### Backend API (Clean Architecture)
* **`GavelPoMobile.Api`**: The ASP.NET Core Web API layer serving as the entry point for the frontend. Handles HTTP requests, routing, and maps them to application logic.
* **`GavelPoMobile.Application`**: The core business logic layer. Implements the CQRS pattern (using MediatR) with clear separation of `Commands` and `Queries` (e.g., `GetAllPurchaseOrdersQuery`, `UpdatePurchaseOrderStatusCommand`).
* **`GavelPoMobile.Domain`**: Contains the core domain models, entities (e.g., `PurchaseOrder`, `PurchaseOrderDetail`, `User`), and aggregate roots.
* **`GavelPoMobile.Infrastructure`**: Implements data access, external services, and identity management. Includes Entity Framework Core configurations, `GavelPoMobileDbContext`, and JWT Authentication.
* **`GavelPoMobile.Contract`**: Contains the Data Transfer Objects (DTOs) and request/response models shared between the API and the client.

## ✨ Features

* **Authentication & Authorization**: Secure login system with JWT token validation.
* **Purchase Order Management**: View lists of pending, incoming, and historical purchase orders.
* **Order Details**: Inspect specific line items and comprehensive details for individual purchase orders.
* **Status Workflows**: Approve, reject, or hold purchase orders and specific line items.
* **Rich UI Dashboards**: Includes integrated DataGrid, Charts, and Scheduler modules for analytics and task management.

## 🛠️ Technologies & Tools

* **Mobile**: [.NET MAUI](https://learn.microsoft.com/en-us/dotnet/maui/)
* **Backend**: ASP.NET Core Web API (.NET 6/7/8)
* **Architecture**: Clean Architecture, CQRS (MediatR)
* **Database**: Entity Framework Core
* **Authentication**: JWT (JSON Web Tokens)
* **UI Controls**: DevExpress for .NET MAUI

## 🚀 Getting Started

### Prerequisites
* [Visual Studio 2022](https://visualstudio.microsoft.com/) (with .NET MAUI workload installed)
* .NET SDK

### Running the Backend API
1. Set `GavelPoMobile.Api` as the startup project.
2. Update the database connection string in `GavelPoMobile.Api/appsettings.json` if necessary.
3. Run the project (F5) to start the API and launch the Swagger documentation.

### Running the Mobile App
1. Set `GavelPoMobile.Maui` as the startup project.
2. Ensure your target emulator (Android/iOS) or physical device is selected.
3. Update the `WebAPIService` base URL in the MAUI project to point to your running local API instance.
4. Run the project to deploy the app to your device or emulator.

## 🔒 License

[Add your license information here]
