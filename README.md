# Entity Types and Mapping in EF Core

This solution demonstrates the concepts of **Entity Types** and **Mapping** in Entity Framework Core. The lecture was divided into five projects, each focusing on a specific aspect of entity mapping and configuration. Below is an overview of each project and its purpose.

---

## 1. **EF009.BasicSetup**
This project provides a basic setup for working with EF Core. It includes:
- **Entities**: `Order`, `OrderDetail`, and `Product`.
- **DbContext**: Configures the database schema and relationships.
- **Key Features**:
  - Basic table mapping.
  - Primary key configuration.
  - Relationships between `Order`, `OrderDetail`, and `Product`.

---

## 2. **EF009.ExcludeEntities**
This project demonstrates how to exclude certain entities from being mapped to the database.
- **Entities**: Includes a `Snapshot` class that is ignored in the database schema.
- **DbContext**:
  - Uses the `Ignore` method to exclude the `Snapshot` entity.
- **Key Features**:
  - Excluding entities from the database schema.
  - Customizing entity configurations.

---

## 3. **EF009.IncludeEntities**
This project focuses on explicitly including entities in the database schema.
- **Entities**: Includes `AuditEntry` to track user actions.
- **DbContext**:
  - Configures `AuditEntry` with a primary key.
- **Key Features**:
  - Explicit inclusion of entities.
  - Demonstrates how to add additional entities to the schema.

---

## 4. **EF009.MappingView**
This project demonstrates how to map database views to entities.
- **Entities**: `OrderWithDetailsView` represents a database view.
- **DbContext**:
  - Maps the `OrderWithDetailsView` entity to a database view using `.ToView()`.
- **Key Features**:
  - Mapping database views to entities.
  - Read-only entities with no primary key.

---

## 5. **EF009.TableValuedFunction**
This project demonstrates how to map table-valued functions (TVFs) to entities.
- **Entities**: Includes `OrderBill` to represent the result of a TVF.
- **DbContext**:
  - Maps the `OrderBill` entity to a table-valued function using `.ToFunction()`.
- **Key Features**:
  - Mapping table-valued functions to entities.
  - Working with computed results in EF Core.

---

## Key Concepts Learned
- **Entity Types**: Understanding how to define and configure entities in EF Core.
- **Mapping**:
  - Mapping entities to tables, views, and functions.
  - Excluding or including entities in the schema.
- **Relationships**: Configuring relationships between entities.
- **Fluent API**: Using the Fluent API for advanced configurations.

---

## How to Run
1. Ensure you have a SQL Server instance running.
2. Update the `appsettings.json` file in each project with the correct connection string.
3. Run the migrations and update the database for each project:
   ```bash
   dotnet ef migrations add InitialCreate
   dotnet ef database update