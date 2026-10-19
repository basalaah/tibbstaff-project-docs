# System Architecture

## 1. Overview

tibbstaff.com is a cross-platform medical recruitment application that began as a Flutter mobile application and later moved toward a Progressive Web App (PWA).

The application supports two primary user roles:

- **Job Seeker:** A healthcare professional looking for employment opportunities.
- **Hiring Institution:** An organization seeking healthcare professionals.

The application uses role-based navigation to present different dashboards, tabs, and workflows to each user type.

## 2. Technology Overview

| Component | Technology | Purpose |
|---|---|---|
| Application framework | Flutter | Cross-platform application development |
| Programming language | Dart | Flutter application implementation |
| Backend platform | Appwrite (self-hosted) | Backend services |
| Containerization | Docker | Supporting self-hosted infrastructure |
| Runtime and tooling | Node.js | Project tooling or supporting components; exact usage to be documented |
| Additional web technologies | TypeScript, JavaScript | Roles to be confirmed for the relevant components |
| Version control | Git and GitHub | Source control and collaboration |
| Development workflow | GitHub Spec Kit | Specification-driven planning and implementation |

## 3. Authentication and Onboarding Flow

The documented user journey follows these steps:

1. The user opens the application.
2. If the user is not authenticated, the application navigates to the sign-in screen.
3. After successful authentication, the application checks the user's profile.
4. If the profile is missing, the application creates one.
5. If the profile has no assigned role, the user is directed to role selection.
6. The user selects either Job Seeker (`باحث عن عمل`) or Hiring Institution (`مؤسسة توظيف`).
7. The selected role is saved through `ProfileService.updateRole(role)`.
8. The application navigates to the post-login shell.
9. The shell reads the assigned role and presents the corresponding navigation and user experience.

## 4. Role-Based Application Structure

### Job Seeker

The job seeker interface includes:

- Dashboard
- Jobs
- Notifications
- Messages
- Profile

The dashboard is rendered through `SeekerDashboardHomeTabView()` in `post_login_shell.dart`.

### Hiring Institution

The hiring institution interface includes its dashboard, job-posting workflow, messaging, and other role-specific sections.

The documented dashboard workflow includes profile completion, verification status, quick statistics, job and applicant review, candidate decisions, and initiating messaging.

The exact tab structure should be kept consistent with the current implementation.

## 5. Application State and Profile Management

The application uses profile information and the assigned user role to determine the appropriate post-login experience.

The documented onboarding flow includes:

- Authentication state checking.
- Profile existence checking and creation.
- Role selection when a role is missing.
- Role persistence through `ProfileService.updateRole(role)`.
- Role-specific navigation after onboarding.

## 6. Mobile-to-PWA Transition

The project initially focused on a mobile application. The team later chose a PWA approach after encountering difficulties with Google Play publication.

The decision aimed to:

- Reduce dependence on app-store distribution.
- Make the platform accessible through a web browser across supported devices.
- Simplify distribution and centrally deliver application updates.
- Reduce the maintenance overhead associated with distributing a mobile application.

A PWA can provide an app-like experience, but installation behavior and available features depend on the browser and device.
