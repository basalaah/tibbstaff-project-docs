# System Architecture

## 1. Overview

**tibbstaff.com** is a medical recruitment platform designed to connect healthcare professionals with institutions seeking to hire them.

The platform supports two primary user roles:

- **Job Seeker:** Healthcare professionals who browse job opportunities, manage their profiles, and submit applications.
- **Hiring Institution:** Organizations that publish job opportunities, review applicants, and manage recruitment activities.

The application uses role-based navigation to provide each user type with an interface and features relevant to their needs.

## 2. Technology Stack

| Technology | Purpose |
|---|---|
| Flutter | Original cross-platform mobile application |
| Dart | Programming language used for the original Flutter application |
| Appwrite (self-hosted) | Backend services |
| Docker | Containerized infrastructure |
| Git and GitHub | Version control and project collaboration |
| GitHub Spec Kit | Specification-driven development workflow |

The project began as a Flutter mobile application and later evolved toward a Progressive Web App (PWA). The technologies listed above reflect the original application and the project's supporting infrastructure.

## 3. Authentication and Onboarding

The authentication and onboarding flow establishes the user's session, profile, and application role.

1. The user opens the application.
2. If the user is not authenticated, the application directs them to the sign-in screen.
3. After successful authentication, the application checks whether a user profile exists.
4. If a profile does not exist, the application creates one.
5. If the profile does not have an assigned role, the user is directed to role selection.
6. The user selects one of two roles:
   - **Job Seeker** (`باحث عن عمل`)
   - **Hiring Institution** (`مؤسسة توظيف`)
7. The selected role is saved through `ProfileService.updateRole(role)`.
8. The application opens the main interface and displays the navigation and features associated with the assigned role.

This flow ensures that users complete the required onboarding steps before accessing their role-specific interface.

## 4. Role-Based Application Structure

The platform provides separate interfaces for job seekers and hiring institutions.

### 4.1 Job Seeker

The job seeker interface includes the following sections:

- **Dashboard:** Provides an overview of relevant account activity.
- **Jobs:** Allows users to browse and search for available opportunities.
- **Notifications:** Provides access to application-related updates.
- **Messages:** Provides access to conversations.
- **Profile:** Allows users to manage their personal and professional information.

Job seekers can explore opportunities, save jobs, submit applications, and manage their recruitment-related activities through the platform.

### 4.2 Hiring Institution

The hiring institution interface focuses on recruitment and applicant management.

Its documented workflows include:

- Managing the institution's profile.
- Creating and managing job postings.
- Reviewing applicants for published positions.
- Viewing recruitment-related statistics.
- Reviewing candidate applications and making hiring decisions.
- Initiating conversations with applicants.

The interface organizes these activities into a role-specific dashboard and navigation structure.

## 5. Profile and Role Management

User profiles and assigned roles determine the application experience presented after authentication.

The onboarding process handles profile existence checks, profile creation when necessary, role selection, and role persistence.

The role update operation is handled through `ProfileService.updateRole(role)`. Once a role has been assigned, the application uses it to determine the appropriate navigation structure and role-specific features.

This approach separates the job seeker and hiring institution experiences while allowing both user types to access the same platform.

## 6. Mobile-to-PWA Evolution

The project initially began as a Flutter mobile application. The team later moved toward a Progressive Web App (PWA) approach after encountering challenges with Google Play publication.

The transition aimed to improve accessibility and simplify distribution by allowing users to access the platform through a web browser, reducing dependence on app-store distribution and enabling centralized application updates.

A PWA can provide an app-like experience across supported devices. Its installation options and available capabilities depend on the browser, device, and implementation.

## 7. Development Approach

The project uses Git and GitHub for version control and GitHub Spec Kit to support a specification-driven development workflow.

This approach helps organize requirements and implementation tasks before development, providing a structured way to plan features and maintain consistency as the application evolves.

The platform is developed iteratively, with attention to user workflows, role-specific functionality, and the overall application experience.
