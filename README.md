
# Online School Management System

A Java web application for managing core school administration workflows through separate administrator, teacher, and student views.

## Overview

The application provides a central interface for maintaining student and teacher records, recording attendance, publishing notices, and managing student results. It is implemented as a traditional Spring MVC web application and is packaged for deployment to Apache Tomcat.

## Features

- Role-based access for administrators, teachers, and students
- Student registration, editing, search, and detail views
- Teacher information management
- Class and subject management
- Attendance entry and search
- Examination result entry and search
- Notice board creation, editing, and display
- JSP-based web interface with Bootstrap styling
- Student image upload support

## Technology Stack

- Java 8
- Spring MVC 4
- Spring JDBC
- MySQL
- JSP and JSTL
- Apache Tomcat 8
- Apache Ant and NetBeans project metadata
- HTML, CSS, JavaScript, and Bootstrap

## Requirements

Install the following before running the application:

- JDK 8
- Apache Tomcat 8.x
- MySQL 5.7 or a compatible MySQL/MariaDB server
- NetBeans 8.x with Java Web support, or an equivalent Ant-compatible IDE
- Git

The project is an older NetBeans web project. It does not use Maven or Gradle and does not contain a `pom.xml` file.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/ganeshkmmaddu/School_management_system.git
cd School_management_system
```

### 2. Create the database

Create a MySQL database named `springschool`, then import the supplied schema and seed data:

```sql
CREATE DATABASE springschool;
```

Import `osmDB20181121 2147.sql` using MySQL Workbench or the command line:

```bash
mysql -u root -p springschool < "osmDB20181121 2147.sql"
```

### 3. Configure the database connection

The connection is configured in `web/WEB-INF/dispatcher-servlet.xml`. Each value can be overridden with an environment variable:

| Environment variable | Default value |
| --- | --- |
| `DB_DRIVER` | `com.mysql.jdbc.Driver` |
| `DB_URL` | `jdbc:mysql://localhost:3306/springschool` |
| `DB_USERNAME` | `root` |
| `DB_PASSWORD` | `root` |

For local development, the defaults work with a MySQL database named `springschool`. For deployment, set these variables in Tomcat or the hosting environment and do not commit credentials to the repository. Do not use the default password in production.

### 4. Configure Tomcat in the IDE

1. Open the project in NetBeans.
2. Register an Apache Tomcat 8 server under **Tools > Servers**.
3. Select the configured server for the project.
4. Clean and build the project.
5. Run or deploy the web application.

The Ant entry point is `build.xml`. NetBeans uses the files under `nbproject` to create the deployable web application.

## Running the Application

After deployment, open:

```text
http://localhost:8080/OnlineSchoolManagementSystem/
```

The exact context path may differ depending on the Tomcat or NetBeans deployment configuration. The application welcome page is `redirect.jsp`.

## Project Structure

```text
src/java/       Java controllers, models, services, and utilities
web/            Web resources, JSP views, CSS, JavaScript, and libraries
web/WEB-INF/    Spring configuration, deployment descriptor, and protected JSPs
nbproject/      NetBeans and Ant build configuration
build.xml       Ant project entry point
osmDB20181121 2147.sql  Database schema and sample data
```

## Continuous Integration

GitHub Actions validates the project structure and XML configuration on every push. A full clean build requires the original NetBeans/Tomcat library configuration, which is environment-specific and is not reproduced by the hosted CI runner.

## Security Notes

This repository contains an educational legacy application. Before using it beyond local development, review and update the following:

- Database credentials and connection settings
- Password storage and authentication logic
- SQL statements and input validation
- File upload validation and access controls
- Production logging, error handling, and secret management

## Contributing

1. Create a feature branch.
2. Keep changes focused and document setup-impacting changes.
3. Test the application locally with the configured Tomcat and MySQL services.
4. Open a pull request with a clear description of the change.

## License

No license file is currently included. Add a license before distributing the project publicly.
