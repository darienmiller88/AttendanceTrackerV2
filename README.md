# Desktop Attendance App

This is version 2.0 of the Attendance App I started last year. I did not get very far at all with the first
version, as I was mostly stuck on the design document. I still plan on including one, but it will be secondary
this time.

### Tech Stack
* [Avalonia](https://avaloniaui.net/)
* [Redis](https://redis.io/)
* [.NET](https://dotnet.microsoft.com/)
* [SQLite](https://www.sqlite.org/)
* [Docker](https://www.docker.com/)

The goal of this project is to create an internal desktop application that allows specialists and staff to manage 
class attendance, store student information locally, and generate pre-styled Excel reports for monthly 
attendance submission. This will solve the current problem of coworkers having to manually input each attendance
record for each student into their attendance sheet, which is time-consuming and prone to errors.

Unlike the original version, this rewrite focuses on building the actual application first, with a cleaner 
architecture and a simpler development process. Since this version is very similar, I can adopt many of the
same features and architectural decisions.

# Purpose of the Project

This application is designed around a real workflow:

* Coworkers manage recurring classes and class offerings
* Students are enrolled into classes
* Attendance is taken daily
* Attendance data is exported into pre-styled Excel sheets at the end of the month

Each user will maintain their own local database instance containing attendance and student information 
relevant to their work.

The project is intentionally designed as an offline-first desktop application rather than a centralized 
web application that exists in the cloud.

### Why a Desktop App Instead of a Web App?

The original idea for this project was a web application. However, after discussing the workflow and data requirements further, a desktop-first architecture made more sense.

The biggest reason was data privacy.

Because the application stores student names and attendance records, there were concerns about storing that information in a centralized cloud database, even with proper authentication and security practices in place.

By moving to a local desktop architecture:

Student data never leaves the user’s machine
No centralized database exists
No public-facing backend or API is required
The application can function completely offline
Security risk is reduced to the security of the individual workstation

SQLite was chosen specifically because it provides a lightweight, serverless database that works extremely well for local-first applications.

Why Avalonia?

Avalonia was chosen over a traditional web stack because the application is fundamentally a desktop workflow tool.

The application relies heavily on:

Data entry forms
Attendance tables and grids
Local database access
File generation and Excel exports
Offline usage

Avalonia also allows the project to remain entirely within the .NET ecosystem while still supporting cross-platform desktop deployment on Windows, macOS, and Linux.

Other desktop frameworks were considered, but Avalonia felt like the best fit because it provides:

Native desktop-style UI patterns
Cross-platform support
XAML-based layouts
Strong MVVM support
Easy integration with existing .NET libraries

This also allows the project to share business logic, database code, and export logic entirely in C# without needing a separate frontend/backend architecture.

Tech Stack
Avalonia
Redis
.NET
SQLite
Docker
Planned Features
Student and specialist management
Attendance tracking
Class and program scheduling
Local SQLite persistence
Excel export generation
Search and filtering
Multi-site support
Offline-first architecture
Current Status

Version 2.0 is currently focused on rebuilding the application architecture from the ground up with:

Improved database design
Cleaner separation of concerns
Proper MVVM structure
Better scalability for future features
Cross-platform desktop deployment support

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Feel free to leave suggestions as well, I'm always looking for ways to improve!

<p align="right">(<a href="#top">back to top</a>)</p>

## License
[MIT](https://choosealicense.com/licenses/mit/)