# Healthcare CRM - Interactive Prototype

## Overview

The **Healthcare CRM - Interactive Prototype** is a front-end web application designed to simulate a healthcare customer relationship management system. It provides a responsive, user-friendly interface for managing patients, appointments, billing, messages, reports, and settings within a healthcare environment. The prototype includes a login system, role-based access control, a dark mode toggle, and modal dialogs for patient management, all styled with Tailwind CSS and enhanced with custom JavaScript functionality.

This project serves as a proof-of-concept or demonstration tool, featuring mock data and simulated interactions rather than a fully functional backend. It is built to be extensible, allowing developers to integrate it with a real backend system (e.g., APIs for authentication, data storage, etc.) in a production environment.

---

## Features

### General
- **Responsive Design**: Adapts seamlessly to various screen sizes (mobile, tablet, desktop) using Tailwind CSS's utility classes.
- **Dark Mode**: Toggleable light/dark themes with persistent state saved in `sessionStorage`.
- **Custom Styling**: Uses the Inter font family and a custom loading spinner for enhanced UX.
- **Accessibility**: Includes ARIA attributes for screen reader support and keyboard navigation.
- **JavaScript Requirement**: Displays a warning if JavaScript is disabled in the browser.

### Login Screen
- **User Authentication**: Mock login with predefined credentials (`admin/password`, `doctor/password`, `staff/password`).
- **Loading State**: Visual feedback (spinner) during login simulation.
- **Error Handling**: Displays error messages for invalid credentials.

### Main Application
- **Sidebar Navigation**: Collapsible menu with icons for Dashboard, Patients, Appointments, Billing, Messages, Reports, and Settings.
- **Role-Based Access Control**: Restricts access to certain pages and actions based on user roles (Administrator, Doctor, Staff).
- **Header**: Displays clinic name, user profile (avatar, name, role), dark mode toggle, and notification bell with badge.
- **Dynamic Pages**: Content switches between pages (e.g., Dashboard, Patients) with permission checks.

### Pages
1. **Dashboard**:
   - Overview cards for Total Patients, Appointments Today, Upcoming Appointments, and Pending Bills.
   - Upcoming Appointments list with mock data.
   - Key Metrics section with placeholder charts (for Administrators and Doctors only).
2. **Patients**:
   - Searchable patient table with columns for ID, Name, DOB, Gender, Contact, and Actions (View, Edit, Delete).
   - Add/Edit patient modals with form validation.
   - Delete confirmation modal.
3. **Appointments**: Placeholder for appointment scheduling (to be implemented).
4. **Billing**: Placeholder for billing and invoicing (Administrator/Staff only).
5. **Messages**: Placeholder for internal messaging (to be implemented).
6. **Reports**: Placeholder for analytics and charts (Administrator/Doctor only).
7. **Settings**:
   - User profile editing (name, optional password change).
   - Notification preferences (in-app toggle).
   - User management table (Administrator only).

### Modals
- **Add Patient**: Form to input patient details (name, DOB, gender, contact, etc.).
- **Edit Patient**: Pre-filled form to update patient information.
- **Delete Confirmation**: Confirms patient deletion with a warning.
- **Notifications**: Displays a placeholder for notifications (currently empty).

---

## Project Structure

```
index.html
├── <head>
│   ├── Meta tags (charset, viewport)
│   ├── Title: "Healthcare CRM - Interactive Prototype"
│   ├── Tailwind CSS CDN
│   ├── Custom Tailwind config (dark mode, font)
│   ├── Google Fonts (Inter)
│   └── Inline CSS (spinner, root variables)
├── <body>
│   ├── Noscript warning
│   ├── Login Screen (div#login-screen)
│   ├── Main App (div#main-app)
│   │   ├── Sidebar (nav#sidebar-nav)
│   │   ├── Header
│   │   └── Main Content (pages: dashboard, patients, etc.)
│   ├── Modals (add-patient, edit-patient, delete-confirm, notification)
│   └── Inline JavaScript (script#script)
```

---

## Technical Details

### Technologies Used
- **HTML5**: Semantic structure with accessibility features.
- **CSS**:
  - **Tailwind CSS**: Utility-first framework for rapid styling.
  - **Custom CSS**: Defines a loading spinner and root variables.
- **JavaScript**:
  - ES6+ with module syntax.
  - DOM manipulation for interactivity.
  - Mock data and simulated async operations.

### Dependencies
- **Tailwind CSS**: Loaded via CDN (`https://cdn.tailwindcss.com`).
- **Google Fonts**: Inter font family (`https://fonts.googleapis.com`).
- **Lucide Icons**: Static SVG icons from CDN (`https://cdn.jsdelivr.net/npm/lucide-static`).

### Key JavaScript Components
- **Mock Data**: `MOCK_USERS` object simulates a user database.
- **State Management**: Uses `currentUser`, `currentPage`, and `sessionStorage` for persistence.
- **Functions**:
  - `login()`: Simulates authentication with a 500ms delay.
  - `navigateTo()`: Switches pages with permission checks.
  - `applyPermissions()`: Hides/shows elements based on user role.
  - `toggleDarkMode()`: Switches themes and saves preference.
  - `openModal()`/`closeModal()`: Manages modal visibility.
  - Settings functions: `loadUserProfile()`, `saveUserProfile()`, etc.

---

## Installation & Usage

### Prerequisites
- A modern web browser (e.g., Chrome, Firefox, Edge).
- JavaScript must be enabled.

### Setup
1. **Clone or Download**: Save the HTML code as `index.html`.
2. **Open in Browser**: Double-click `index.html` or serve it via a local server (e.g., `npx live-server`).
   - No additional dependencies need to be installed since all resources are loaded via CDN.

### Usage Instructions
1. **Login**:
   - Use credentials: `admin/password`, `doctor/password`, or `staff/password`.
   - Click "Login" to access the main app.
2. **Navigate**:
   - Use the sidebar to switch between pages (e.g., Dashboard, Patients).
   - Some pages/buttons are restricted by role (e.g., Billing for Administrator/Staff).
3. **Interact**:
   - Toggle dark mode via the sun/moon icon in the header.
   - Click the notification bell to view the modal (currently empty).
   - On the Patients page, add/edit/delete patients using the respective buttons.
4. **Logout**: Click "Logout" in the sidebar to return to the login screen.

---

## Limitations & Notes
- **Prototype Nature**: This is a front-end-only demo with mock data. No real backend integration exists.
- **Placeholder Content**: Pages like Appointments, Billing, Messages, and Reports contain minimal content.
- **Patient Deletion**: Only removes rows from the DOM, not persistent storage.
- **Password Handling**: Password changes in Settings are session-only and not reflected in `MOCK_USERS`.
- **Charts**: Dashboard metrics use placeholders (`Chart Area`) instead of real charts.

---

## Future Enhancements
- **Backend Integration**: Connect to a server for real authentication, data storage, and CRUD operations.
- **Chart Library**: Integrate Chart.js or similar for Dashboard metrics.
- **Full CRUD**: Implement complete Create, Read, Update, Delete functionality for patients and other entities.
- **Notifications**: Add real-time notifications with WebSocket or polling.
- **Form Validation**: Enhance client-side and server-side validation for all forms.

---

## License
This project is unlicensed and intended for educational or demonstration purposes. Feel free to modify and adapt it as needed.
