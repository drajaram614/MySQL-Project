## Overview

### Mobile Car Wash and Detailing Web Application

I developed a comprehensive web application that showcases a fully functional MySQL database, designed specifically for a Mobile Car Wash and Detailing business. The project incorporates ten complex tables that are meticulously structured to ensure data integrity and efficiency. Key features of the database include:

- **Primary and Foreign Keys**: Each table utilizes primary keys to uniquely identify records and foreign keys to establish relationships between tables, ensuring referential integrity.

- **Data References and Constraints**: Implemented constraints to enforce data validation rules, maintaining high data quality throughout the application.

- **Normalization**: The database is normalized to eliminate redundancy and improve data organization, facilitating easier access and manipulation of information.

#### Application Features:
- **Customer Service Request Form**: Users can fill out a detailed form to request services at their preferred location, streamlining the booking process.

- **Dynamic Pricing Model**: Pricing is calculated based on vehicle type and size, allowing customers to choose from various packages and services tailored to their needs.

- **Customer Reviews**: The application includes a section for customer reviews, providing valuable feedback and enhancing user engagement.

- **Employee Wage Adjustment**: A mechanism is in place to adjust employee wages based on customer ratings, promoting high-quality service and incentivizing performance.

This project not only highlights my skills in database design and web development but also demonstrates my ability to create functional applications that meet real-world business needs. 


## Website Structure

### 1. Main Webpage
![Main Webpage](path/to/main_webpage_image.jpg)
The landing page features an overview of the car wash services offered, customer testimonials, and links to various sections of the website.

### 2. Book Appointment Page
![Book Appointment Page](path/to/book_appointment_image.jpg)
Customers can select their preferred services, fill out their details, and schedule an appointment through this form.

### 3. Package Price Page
![Package Price Page](path/to/package_price_image.jpg)
This page lists all available car wash packages, detailed descriptions, and their respective prices.

### 4. Check Appointment Page
![Check Appointment Page](path/to/check_appointment_image.jpg)
Users can check their appointment status and details here.

### 5. Customer Service Page
![Customer Service Page](path/to/customer_service_image.jpg)
A dedicated page for customers to reach out for support and queries regarding the services offered.

## SQL Database Components

### ER Diagram
![ER Diagram](path/to/er_diagram_image.jpg)
- **Overview:**
  - Illustrates relationships between entities in the database.
  - Highlights one-to-many and one-and-only relationships.

- **One-to-Many Relationships:**
  - Example: Customer to Appointments, Vehicle to Appointments.

- **One-and-Only Relationships:**
  - Emphasizes unique associations, crucial for maintaining data integrity.

- **Optional Relationships:**
  - Examples: Customer Review, Appointment Check.

- **Mandatory Relationships:**
  - Examples: Vehicle Description for Appointment, Car Wash/Detail Package for Appointment.

### Tables Overview

#### Vehicle Table

![Vehicle Table](path/to/vehicle_table_image_1.jpg)

- **Purpose:** Stores information about vehicles registered by customers.
- **Attributes:** VehicleID, CustomerID (FK), Year, Make, Model, VehicleType, VehicleSize, NumberOfDoors, ExteriorColor, InteriorColor, InteriorMaterial, FloorMatType.
- **Primary Key:** VehicleID.
- **Integrity Enforcement:** FK constraint on CustomerID for referential integrity.

#### vehicletypelimits Table

![vehicletypelimits Table](path/to/vehicletypelimits_table_image_2.jpg)

- **Purpose:** Stores limits and specifications for different vehicle types.
- **Attributes:** TypeLimitID, CarType, CarSize, NumberOfDoors.
- **Primary Key:** TypeLimitID.

#### Appointment Table

![Appointment Table](path/to/appointment_table_image_3.jpg)

- **Purpose:** Manages appointments made by customers.
- **Primary Key:** AppointmentID.
- **Foreign Keys:** VehicleID and PackageID.
- **Integrity Enforcement:** FK constraints for data consistency.

#### Appointment Service Table

![Appointment Service Table](path/to/appointment_service_table_image_4.jpg)

- **Purpose:** Represents the many-to-many relationship between appointments and services.
- **Attributes:** AppointmentID and ServiceID.
- **Integrity Enforcement:** FK constraints.

#### Package Table

![Package Table](path/to/package_table_image_5.jpg)

- **Purpose:** Manages details of car wash packages.
- **Attributes:** PackageID, PackageName, Description, Price.
- **Primary Key:** PackageID.
- **Integrity Enforcement:** Primary key and check constraints for data accuracy.

#### Service Table

![Service Table](path/to/service_table_image_6.jpg)

- **Purpose:** Stores information about car wash services.
- **Attributes:** ServiceID, ServiceName, Description, Price.
- **Primary Key:** ServiceID.

#### PackageService Table

![PackageService Table](path/to/packageservice_table_image_7.jpg)

- **Purpose:** Associates car wash packages with services.
- **Attributes:** PackageID and ServiceID (Composite Key).
- **Integrity Enforcement:** FK constraints for referential integrity.

#### Customer Table

![Customer Table](path/to/customer_table_image_8.jpg)

- **Purpose:** Stores information about customers.
- **Attributes:** CustomerID, FirstName, LastName, Email, Phone, Address.
- **Primary Key:** CustomerID.
- **Integrity Enforcement:** Unique constraints on Email and Phone.

#### CustomerReview Table

![CustomerReview Table](path/to/customerreview_table_image_9.jpg)

- **Purpose:** Records reviews from customers.
- **Attributes:** ReviewID, CustomerID, AppointmentID, Date, Rating, Comments, EmployeeID.
- **Primary Key:** ReviewID.

#### Employee Table

![Employee Table](path/to/employee_table_image_10.jpg)

- **Purpose:** Stores information about employees.
- **Attributes:** EmployeeID, FirstName, LastName, Position, Wage, Rating.
- **Primary Key:** EmployeeID.

### Images for SQL Tables
Below are the images representing each SQL table structure:

11. ![Table 11](path/to/table_11_image_11.jpg)
12. ![Table 12](path/to/table_12_image_12.jpg)
13. ![Table 13](path/to/table_13_image_13.jpg)
14. ![Table 14](path/to/table_14_image_14.jpg)
15. ![Table 15](path/to/table_15_image_15.jpg)
16. ![Table 16](path/to/table_16_image_16.jpg)
17. ![Table 17](path/to/table_17_image_17.jpg)

## Procedures, Views, Triggers, and Functions
### PackageDetails View

![Table 11](path/to/table_11_image_11.jpg)

- **Purpose:** Overview of car wash packages and included services.
- **Attributes:** PackageID, PackageName, PackageDescription, PackagePrice, IncludedServices, TotalServices.

### Get Vehicle Sizes Function

![Table 12](path/to/table_12_image_12.jpg)

- **Purpose:** Retrieves available sizes for a vehicle type.
- **Input:** car_type (VARCHAR).
- **Output:** vehicle_sizes (VARCHAR).

### Get Number Of Doors Function

![Table 13](path/to/table_13_image_13.jpg)

- **Purpose:** Retrieves number of doors for a vehicle type.
- **Input:** car_type (VARCHAR).
- **Output:** num_doors (VARCHAR).

### Calculate Adjusted Package Price Function

![Table 14](path/to/table_14_image_14.jpg)

- **Purpose:** Calculates adjusted price for a car wash package.
- **Input:** packageID (INT), vehicleTypeLimitID (INT).
- **Output:** adjustedPrice (DECIMAL).

### Adjust Employee Wage Procedure

![Table 14](path/to/table_15_image_14.jpg)

- **Purpose:** Adjusts employee wages based on average ratings.
- **Input:** empID (INT).

### Trigger: Update_Employee_Rating

![Table 14](path/to/table_16_image_14.jpg)

- **Purpose:** Updates employee ratings on new reviews.
- **Event:** AFTER INSERT ON CustomerReview.

## Isolation Level
- **Isolation Level Used:** REPEATABLE-READ
- **Reason:** Ensures data consistency and prevents phantom reads during critical operations like appointments and reviews.
