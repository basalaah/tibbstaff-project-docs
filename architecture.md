# System Architecture

## 1. Overview

tibbstaff.com is a medical recruitment application built with Flutter. It initially started as a mobile application and later moved toward a Progressive Web App (PWA) to simplify distribution and support access through compatible web browsers.

The platform has two primary user roles:

- **Job Seeker:** A healthcare professional looking for employment opportunities.
- **Hiring Institution:** An organization recruiting healthcare professionals.

The application uses the user's authentication state, profile information, and assigned role to determine the appropriate post-login experience.

## 2. Technology Overview

| Component | Technology | Purpose |
|---|---|---|
| Application framework | Flutter | Cross-platform user interface |
| Programming language | Dart | Flutter application implementation |
| Backend platform | Appwrite (self-hosted) | Backend services |
| Infrastructure | Docker | Containerization for self-hosted services |
| Additional web technologies | TypeScript and JavaScript | Supporting components or tooling; exact roles depend on implementation |
| Runtime and tooling | Node.js | Supporting tooling or components, where applicable |
| Version control | Git and GitHub | Source control and collaboration |
| Development workflow | GitHub Spec Kit | Specification-driven planning and implementation |

## 3. Authentication and Onboarding

The documented authentication and onboarding flow follows these steps:

1. The user opens the application.
2. If the user is not authenticated, the application directs them to the sign-in screen.
3. After successful authentication, the application checks the user's profile.
4. If the profile is missing, the application creates one.
5. If the profile has no assigned role, the user is directed to role selection.
6. The user selects one of the following roles:
   - `باحث عن عمل` — Job Seeker
   - `مؤسسة توظيف` — Hiring Institution
7. The selected role is saved through `ProfileService.updateRole(role)`.
8. The application navigates to the post-login shell.
9. The shell reads the assigned role and displays the corresponding navigation and user experience.

## 4. Post-Login Application Structure

The post-login shell provides role-specific navigation and entry points to the application's main features.

### Job Seeker

The documented navigation includes:

- Dashboard
- Jobs
- Notifications
- Messages
- Profile

The job seeker dashboard is rendered through `SeekerDashboardHomeTabView()` in `post_login_shell.dart`.

The dashboard workflow includes summary cards, invitations, applications, saved jobs, and messages.

### Hiring Institution

The institution experience includes:

- Dashboard
- Job posting
- Applicant management
- Messaging
- Other institution-specific sections

The dashboard workflow includes profile completion, verification status, quick statistics, applicants grouped by job, candidate decisions, and conversation initiation.

The exact tab labels and navigation structure should match the current implementation.

## 5. Job Access and Application Flow

Job seekers can browse jobs, save or unsave listings, and follow the application workflow.

Access to job-related features is gated by profile requirements. The application checks the relevant profile conditions before allowing users to proceed.

The detailed conditions and behavior should be documented against the current implementation rather than inferred from the interface alone.

## 6. Messaging and Conversations

The application includes a messaging entry point and a conversation system.

Documented functionality includes:

- Access to conversations through the messaging interface.
- Unread-message badge support.
- Deep links that direct users to support conversations.

The exact notification triggers, unread-count behavior, and supported deep-link destinations should be verified against the current application.

## 7. Notifications

The notification system includes a unified alerts entry point and badge behavior.

However, the notification functionality is described as planned and partially wired up, with feature-flag-based rollout.

This means the notification interface and some supporting logic exist, but the full functionality should not be described as completely implemented or universally available until verified.

## 8. Verification Workflow

The documented workflows include institution verification status and review of applicant documents, with a verification badge associated with the relevant review process.

The exact entity being verified, reviewer permissions, document-validation criteria, badge rules, and current implementation status should be confirmed before describing the process as fully operational.

## 9. Mobile-to-PWA Transition

The project initially focused on a Flutter mobile application. The team later shifted toward a PWA after encountering difficulties with Google Play publication.

The decision aimed to simplify distribution, support access across compatible devices, and make application updates easier to deliver.

PWA capabilities, installation behavior, and platform-specific features depend on browser and device support.

## 10. Security and Implementation Boundaries

The application's detailed database schema, access-control implementation, backend configuration, and deployment architecture are not reproduced here because the source code is private.

This document describes the documented application flows and technology choices. Further implementation details should be added only after verifying them against the current codebase.

