# Features and User Workflows

## 1. Platform Overview

tibbstaff.com is a medical recruitment platform that connects healthcare professionals with institutions seeking to recruit them.

The platform supports two user roles, each with a dedicated interface and recruitment-related workflows.

| User Role | Description |
|---|---|
| Job Seeker (`باحث عن عمل`) | Explore job opportunities, manage a professional profile, submit applications, and track recruitment activity. |
| Hiring Institution (`مؤسسة توظيف`) | Publish job opportunities, review applicants, manage recruitment activities, and communicate with candidates. |

## 2. Authentication and Onboarding

The platform uses a profile-aware onboarding flow to direct users to the appropriate interface.

1. Unauthenticated users are directed to sign in.
2. After authentication, the application checks whether a user profile exists.
3. If necessary, a profile is created.
4. Users without an assigned role are prompted to select one.
5. Users choose Job Seeker (`باحث عن عمل`) or Hiring Institution (`مؤسسة توظيف`).
6. The selected role is saved through `ProfileService.updateRole(role)`.
7. The application displays the interface and navigation associated with the selected role.

This process establishes the user's profile and role before they proceed to the main application interface.

## 3. Job Seeker Features

### Dashboard

The job seeker dashboard brings together key recruitment activities, including applications, invitations, saved jobs, and messages.

### Job Discovery

Job seekers can browse available job listings and use search and filtering functionality to find relevant opportunities.

### Job Applications

Users can submit applications through the platform and access information about their application activity.

### Saved Jobs

Users can save job opportunities and access them later through the saved-jobs section.

### Notifications and Messaging

Dedicated sections provide access to notifications and conversations relevant to the user's recruitment activities.

### Profile Management

Job seekers can access their profiles and manage their personal and professional information.

## 4. Hiring Institution Features

### Institution Dashboard

The institution dashboard provides access to recruitment activities and institution-related information, including profile completion, verification status, and quick statistics.

### Job Posting

Hiring institutions can use the job-posting workflow to publish opportunities for healthcare professionals.

### Applicant Management

Institutions can review applicants associated with their job postings, organize applicants by position, and record candidate decisions, including acceptance or rejection.

### Messaging

Institutions can initiate conversations with candidates as part of the recruitment process.

## 5. Role-Based Navigation

The application uses the user's assigned role to determine the navigation and interface presented after onboarding.

The job seeker interface provides access to the dashboard, job listings, notifications, messages, and profile management.

The hiring institution interface provides access to its dashboard, job-posting and applicant-management workflows, messaging, and other institution-specific sections.

This role-based structure keeps the main workflows relevant to each user group.

## 6. User Workflow Summary

The platform organizes its main workflows around two complementary recruitment journeys.

**Job seeker journey:** Sign in → Complete profile and onboarding → Discover opportunities → Save jobs or apply → Follow recruitment activity → Communicate through messaging.

**Hiring institution journey:** Sign in → Complete institution onboarding → Manage institution profile → Publish job opportunities → Review applicants → Make candidate decisions → Communicate with candidates.

These workflows describe the platform's intended recruitment experience and the functionality outlined in its project documentation.
