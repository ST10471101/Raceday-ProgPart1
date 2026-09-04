RaceDay System
Project Description

RaceDay is a web-based event management system designed to make it easier to organise and participate in running and racing events.
The system allows **Organisers** to create and manage race events, categories and routes, while **Participants** can view available events and enrol in races.
The system also provides event-related information such as race routes and weather information. The API uses role-based access control to make sure that users can only perform actions they are authorised to perform.

The main purpose of RaceDay is to provide a centralised system where race organisers can manage events and participants can easily find and register for races.

Main Objectives
The RaceDay System aims to:
* Allow users to register and log in securely.
* Allow Organisers to create and manage race events.
* Allow Organisers to create and manage race categories.
* Allow Organisers to manage event routes.
* Allow Participants to view available races.
* Allow Participants to enrol in race categories.
* Allow Participants to view and manage their enrolments.
* Provide weather information associated with an event.
* Protect system features using role-based authorisation.
* Provide a REST API for communication between the application and database.

               User Roles

The Organiser is responsible for managing RaceDay events.
An Organiser can:
* Create new race events.
* View event information.
* Update event details.
* Delete events.
* Create race categories.
* Update race categories.
* Delete race categories.
* Create event routes.
* Update event routes.
* Delete event routes.
* View participant enrolments for their events.
* Manage information related to their events.
* 
 Participant
The Participant is a user who wants to take part in a RaceDay event.

A Participant can:
* Register for an account.
* Log in to the system.
* View available race events.
* View event details.
* View race categories.
* Enrol in a race category.
* View their own enrolments.
* Cancel their enrolment.
* Update their personal profile.

Participants cannot create or delete events because those functions are restricted to Organisers.

Authentication and Security
RaceDay uses authentication and role-based authorisation.

Users must log in before accessing protected features.

The system uses different permissions depending on the user's role:

 Main API Features

The RaceDay REST API contains endpoints for:

### Authentication

```text
POST /api/auth/register
POST /api/auth/login
```

### Users

```text
GET /api/users/me
PUT /api/users/me
```

### Events

```text
GET /api/events
GET /api/events/{id}
POST /api/events
PUT /api/events/{id}
DELETE /api/events/{id}
```

### Categories

```text
GET /api/events/{eventId}/categories
GET /api/categories/{id}
POST /api/events/{eventId}/categories
PUT /api/categories/{id}
DELETE /api/categories/{id}
```

### Enrolments

```text
POST /api/events/{eventId}/enrollments
GET /api/events/{eventId}/enrollments
GET /api/users/me/enrollments
DELETE /api/enrollments/{id}
```

### Routes

```text
GET /api/events/{eventId}/route
POST /api/events/{eventId}/route
PUT /api/routes/{id}
DELETE /api/routes/{id}
```

### Weather

```text
GET /api/events/{eventId}/weather
```

---

## 🗄️ Main System Entities

The main entities used by the RaceDay System include:

* **User**
* **Organiser**
* **Participant**
* **Event**
* **Category**
* **Enrolment**
* **Route**
* **Weather**

These entities are connected through relationships in the database to ensure that event, user and enrolment information can be managed correctly.

---

## ⚙️ Technologies Used

* **C#**
* **.NET 8**
* **ASP.NET Core Web API**
* **REST API**
* **SQL Database**
* **Entity Framework Core**
* **GitHub**
* **GitHub Actions**
* **JSON**

---

## 🔄 CI/CD

RaceDay uses **GitHub Actions** to automate the build and deployment pipeline.

The CI/CD workflow automatically:

1. Checks out the latest source code.
2. Installs the required .NET version.
3. Restores project dependencies.
4. Builds the application.
5. Runs automated tests.
6. Publishes the application.
7. Uploads the published application as a GitHub Actions artifact.

This helps identify errors early and makes the development process more reliable.

---

## 📁 Project Structure

```text
RaceDay
│
├── .github
│   └── workflows
│       └── dotnet-ci-cd.yml
│
├── Controllers
│
├── Models
│
├── Data
│
├── Services
│
├── DTOs
│
├── Migrations
│
├── Properties
│
├── appsettings.json
│
├── Program.cs
│
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone YOUR-GITHUB-REPOSITORY-URL
```

### 2. Open the project

Open the RaceDay project in **Visual Studio** or **Visual Studio Code**.

### 3. Restore dependencies

```bash
dotnet restore
```

### 4. Build the project

```bash
dotnet build
```

### 5. Run the application

```bash
dotnet run
```

### 6. Test the API

Once the application is running, API endpoints can be tested using tools such as **Swagger**, **Postman**, or another REST API client.

---

## 🧪 Testing

The API should be tested to ensure that:

* Users can register successfully.
* Users can log in.
* Organisers can manage events.
* Organisers can manage categories.
* Organisers can manage routes.
* Participants can enrol in races.
* Participants can cancel enrolments.
* Unauthorised users cannot access protected features.
* Invalid requests return appropriate HTTP status codes.

---

## 📊 API Response Codes

| Status Code          | Meaning                              |
| -------------------- | ------------------------------------ |
| **200 OK**           | Request completed successfully       |
| **201 Created**      | New resource successfully created    |
| **204 No Content**   | Resource successfully deleted        |
| **400 Bad Request**  | Invalid request or information       |
| **401 Unauthorized** | User is not authenticated            |
| **403 Forbidden**    | User does not have permission        |
| **404 Not Found**    | Requested resource does not exist    |
| **409 Conflict**     | Request conflicts with existing data |

---

## 👨‍💻 Project

**Project Name:** RaceDay System

**Purpose:** Race event management and participant enrolment.

**Main Users:** Organisers and Participants.

**Repository:** GitHub

---

## 📄 Conclusion

RaceDay provides a centralised solution for managing running and racing events. By separating Organiser and Participant responsibilities, the system provides appropriate access to different features while protecting restricted functionality.

The REST API allows the different parts of the system to communicate with the database, while GitHub Actions provides an automated CI/CD process for building, testing and publishing the application.
