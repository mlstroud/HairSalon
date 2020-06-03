# _Hair Salon_

#### _Epicodus Project May 29, 2020_

#### By _**Matt Stroud**_

## Description

_An Epicodus individual project focused on creating a RESTful web app using C#'s MVC._  
_The user manages a hair salon and is able to add stylits, add clients to a stylist, and view/edit stylists and clients._ 


## Specs
### User Stories
* As the salon owner, I need to be able to see a list of all stylists.
* As the salon owner, I need to be able to select a stylist, see their details, and see a list of all clients that belong to that stylist.
* As the salon owner, I need to add new stylists to our system when they are hired.
* As the salon owner, I need to be able to add new clients to a specific stylist. I should not be able to add a client if no stylists have been added.

### Behaviors
| Behavior                                                   | Input                            | Output                                 |
|:-----------------------------------------------------------|:---------------------------------|---------------------------------------:|
| Program will allow user to view all stylists.              | "Stylists"                            | "Sherry", "Chelsea"                      |
| Program will allow user to view all clients.               | "Clients"                             | "Greg", "Thomas"                      |
| Program will allow user to view all clients for a stylist. | "Sherry"                         | "Greg"                          |
| Program will allow user to add a stylist.                  | "Sunny"                         | "Sherry", "Chelsea", "Sunny"                |
| Program will allow user to add a client to a stylist.      | "Tia" -> "Chelsea"              | "Chelsea" -> "Tia" |
| Program will allow user to edit a stylist.                 | "Sherry" -> "Sherry Anderson"   | "Sherry Anderson", "Chelsea", "Sunny |
| Program will allow user to edit a client.                  | "Tia" -> Stylist: "Sunny"       | "Chelsea" -> "" - "Sunny" -> "Tia" |

### RESTful Routing
| Path                     | Route          | Method |
|:-------------------------|:---------------|-------:|
| /                        | Home->Index    | Get    |
| /Stylists                | Stylists->Index| GET    |
| /Stylists/Create         | Stylists->Create | GET    |
| /Stylists/Create           | Stylists->Create | POST   |
| /Stylists/Details/{id}   | Stylists->Details  | GET    |
| /Stylists/Edit/{id}     | Stylists->Edit  | GET    |
| /Clients                | Clients->Index    | GET    |
| /Clients/Create     | Clients->Create | GET   |
| /Clients/Create     | Clients->Create | POST |
| /Clients/Details/{id} | Clients->Details | GET |
| /Clients/Edit/{id} | Clients->Edit | GET

### Stretch Goals
 * Add Styling (Complete)
 * Add Edit Functionality (Complete)
 * Add Delete Functionality (In Progress)
 * Add Search Functionality (Complete)
 * Add Appointment Functionality

## Setup/Installation Requirements
> This application requires the .NETCore SDK - [Find your version here](https://dotnet.microsoft.com/download/dotnet-core/2.2)

1. Create a VendorOrderTracker.Solution directory.
```
mkdir VendorOrderTracker.Solution
```
2. Navigate inside your new directory.
```
cd VendorOrderTracker.Solution
```
3. Clone this repository to your directory.
```
git clone https://github.com/mlstroud/HairSalon.git
```
4. Setup Database - Run the MySQL commands below:
```
CREATE DATABASE `matt_stroud`;

USE `matt_stroud`;

CREATE TABLE `clients` (
  `ClientId` int NOT NULL AUTO_INCREMENT,
  `Name` varchar(255) NOT NULL,
  `Description` varchar(255) NOT NULL,
  `StylistId` int NOT NULL,
  PRIMARY KEY (`ClientId`)
);

CREATE TABLE `stylists` (
  `StylistId` int NOT NULL AUTO_INCREMENT,
  `Name` varchar(255) NOT NULL,
  PRIMARY KEY (`StylistId`)
);
```
5. Run the application with the following command:
```
dotnet run
```
6. Open URL in browser:
```
http://localhost:5000/
```

## Known Bugs

* Deletion of Stylists is not yet supported until workaround for re-assigning their clients is implemented.
 
## Support and contact details

_Have a bug or an issue with this application? [Open a new issue](https://github.com/mlstroud/HairSalon/issues) here on GitHub._

## Technologies Used

* C#
* .NET Core
* MVC
* Entity Framework Core
* RESTful Design
* MSTest
* Git

### License

This software is licensed under the MIT license.

Copyright © 2020 **_Matt Stroud_**