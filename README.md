
## Short Overview

**Hospital Management App** is a full-stack MERN application that helps a hospital manage its day-to-day records. 
It provides dedicated views for **Appointments**, **Doctors**, and **Patients**, where staff can add, view, edit, and delete records through a clean, responsive UI. 
The front end is a single-page React app that talks to a Node/Express REST API backed by MongoDB, so every change is persisted to the database.

## Use Cases

- **As hospital staff**, I can view a list of all appointments, doctors, and patients at a glance.
- **As a receptionist**, I can schedule a new appointment by entering the patient name, doctor name, and date.
- **As an administrator**, I can add new doctors with their name and specialty, and update or remove them when they leave.
- **As a records clerk**, I can register new patients with their name, age, and gender, then edit or delete their details as needed.
- **As the hospital**, the app provides a single place to keep patient, doctor, and appointment records consistent across all three resources.

## Technical Functionality (High-Level)

- **Backend (REST API):** Node.js + Express exposes full CRUD routes for three resources: appointments (`routes/appointments.js`), doctors (`routes/doctors.js`), and patients (`routes/patients.js`). The server is bootstrapped in `server.js`, which mounts each router and connects to MongoDB.
- **Database:** MongoDB with Mongoose. Data is modeled with three schemas — `Appointment` (patientName, doctorName, date), `Doctor` (name, specialty), and `Patient` (name, age, gender) — in `models/Appointment.js`, `models/Doctor.js`, and `models/Patient.js`.
- **Frontend (React):** A single-page app with navigation via React Router and views for Appointments, Doctors, and Patients. Reusable presentational components (`AppointmentCard`, `DoctorCard`, `PatientCard`) render each record with Edit/Delete actions.
- **API integration:** Axios is used in each view to `GET`, `POST`, and `DELETE` data from the API (`http://localhost:5000`). Local component state tracks the list, the form, and whether the user is in add or edit mode.
- **Security & quality:** Request bodies are parsed with `body-parser`, CORS is enabled for local development, and failed requests are caught and logged so the UI stays stable.

## Lessons Learned

- Building a REST API and consuming it from React clarified how the client, server, and database interact through a well-defined interface.
- Splitting models and routes per resource kept the backend organized and made each CRUD endpoint easy to reason about.
- Using Mongoose schemas emphasized the value of defining required fields and types up front.
- Managing lists, forms, and edit state with React Hooks (`useState`, `useEffect`) reinforced how React handles shared application state across views.
- Handling promises with `.then()`/`.catch()` in both Express routes and Axios calls showed the importance of consistent error handling.

## Future Features

- [] JWT-based authentication and role-based access (admin, doctor, receptionist).
- [] Link appointments to actual patient and doctor records instead of free-text names.
- [] A dashboard with statistics (appointments per day, doctors per specialty).
- [] Search, filtering, and pagination for large record sets.
- [] Appointment scheduling with time slots and conflict detection.
- [] Deployment of the API and front end to a hosted environment.

---


## 🚀 Getting Started

```bash
**front-end**
cd frontend
npm install
npm start

**back-end**
cd backend
npm install
node server.js

```

---

# 📚 References
- https://react.dev/
- https://reactrouter.com/
- https://expressjs.com/
- https://mongoosejs.com/
- https://nodejs.org/
- https://www.mongodb.com/docs/manual/indexes/
- https://www.geeksforgeeks.org/mern/hospital-management-application-using-mern-stack/
# Scrum 

https://capstone-community-market-app.atlassian.net/jira/software/projects/SCRUM/boards/1?filter=&groupBy=none

# 📅 Timeline

**Due Date:** 09/20/2026
