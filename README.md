# FastTrack Logistics

FastTrack Logistics is a desktop logistics management system built in Java using Object-Oriented Programming principles. The application uses a modular MVC-style architecture with DAO persistence, Java Swing user interface panels, and JDBC database connectivity.

## Overview

The application helps logistics operators manage shipments, delivery personnel, delivery scheduling, driver assignments, shipment tracking, notifications, and reporting.

## Main Functions

- Manage Shipments
  - Create, update, and delete shipment records
  - Store sender/receiver details, package contents, weight, dimensions, and current location
  - Track delivery status, scheduled delivery date, estimated delivery time, and assigned driver

- Manage Delivery Personnel
  - Add, edit, and remove delivery personnel records
  - Store contact details, vehicle information, availability status, and current route

- Schedule Deliveries
  - Schedule delivery jobs by linking shipments, delivery personnel, dates, and times
  - Support delivery workflow planning and assignment

- Assign Drivers
  - Assign drivers to shipments and update route assignments
  - Coordinate driver availability with shipment requirements

- Track Shipments
  - View shipment status and location details
  - Monitor estimated delivery time and progress in the system

- Notifications
  - Customer notifications: record and send notifications linked to shipments
  - Personnel notifications: send updates and assignments to delivery personnel

- Reports
  - Generate monthly logistics reports
  - Include performance metrics such as on-time delivery rate, average delivery time, shipment volume, and route summaries

## Architecture

The project follows a layered design:

- `src/Model/` — domain entity classes such as `Shipment`, `DeliveryPersonnel`, `Notification`, and `Report`
- `src/DAO/` — data access objects that handle CRUD operations with the database
- `src/controller/` — business logic controllers that mediate between views and DAOs
- `src/view/` — Java Swing panels for each UI section of the application
- `src/util/DatabaseConnection.java` — shared JDBC connection utility
- `src/MainApplication.java` — main entry point that configures DAOs, controllers, and the tabbed UI

## Technology Stack

- Java SE (Java 8+ recommended)
- Java Swing for desktop UI
- JDBC for database access
- MySQL (or compatible SQL database) via `com.mysql.cj.jdbc.Driver`

## Project Structure

- `src/MainApplication.java` — application launcher and tabbed UI container
- `src/DAO/` — `ShipmentDAO`, `DeliveryDAO`, `DeliveryPersonnelDAO`, `NotificationDAO`, `ReportDAO`
- `src/controller/` — `ShipmentController`, `DeliveryController`, `DeliveryPersonnelController`, `NotificationController`, `ReportController`
- `src/Model/` — `Shipment`, `Delivery`, `DeliveryPersonnel`, `Notification`, `Report`
- `src/view/` — UI panels including:
  - `ShipmentPanel`
  - `PersonnelPanel`
  - `ScheduleDeliveriesPanel`
  - `TrackShipmentsPanel`
  - `AssignDriversPanel`
  - `ReportPanel`
  - `CustomerNotificationsPanel`
  - `PersonnelNotificationsPanel`
- `src/util/DatabaseConnection.java` — database connection utility with URL and credential placeholders

## Run Instructions

1. Update the database configuration in `src/util/DatabaseConnection.java`:
   - `DB_URL`
   - `DB_USER`
   - `DB_PASSWORD`

2. Ensure the MySQL JDBC driver JAR is on the classpath.

3. Compile the project from the root folder:

```powershell
javac -d out src/MainApplication.java src/DAO/*.java src/controller/*.java src/view/*.java src/util/*.java src/Model/*.java
```

4. Run the application:

```powershell
java -cp out MainApplication
```

## Database Notes

- The application uses JDBC to connect to a SQL database.
- The `DatabaseConnection` utility currently points to a placeholder MySQL database URL.
- You must create the required database and tables before running the application, or update the connection settings to match your environment.


