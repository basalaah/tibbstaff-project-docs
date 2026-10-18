# Features and User Workflows

## 1. User Roles

The platform supports two primary user roles.

| Role | Purpose |
|---|---|
| Job Seeker (`باحث عن عمل`) | Explore employment opportunities and manage job-seeking activities |
| Hiring Institution (`مؤسسة توظيف`) | Publish job opportunities and manage recruitment activities |

## 2. Authentication and Onboarding

The application follows a profile-aware onboarding process.

1. Unauthenticated users are directed to sign in.
2. After successful authentication, the application checks whether a profile exists.
3. A missing profile is created.
4. Users without an assigned role are directed to onboarding.
5. Users select their role.
6. The role is persisted through `ProfileService.updateRole(role)`.
7. The application opens the post-login shell and displays the appropriate interface.

## 3. Job Seeker Features

### Dashboard

The job seeker dashboard provides an overview of job-seeking activities.

The documented workflow includes checking invitations, applications, saved jobs, and messages.

### Job Discovery

Job seekers can access job listings and use search and filtering features to explore available opportunities.

### Job Applications

Job seekers can apply for jobs through the platform and access application-related information.

### Saved Jobs

The documented user journey includes access to saved jobs.

### Notifications and Messaging

Job seekers have dedicated navigation for notifications and messages, including access to relevant conversations.

### Profile Management

Job seekers have a profile section for managing their profile information.

## 4. Hiring Institution Features

### Institution Dashboard

The documented dashboard workflow includes:

- Profile completion information.
- Institution verification status.
- Quick statistics.
- Access to job and applicant management workflows.

### Job Posting

Hiring institutions have access to a job-posting workflow for publishing recruitment opportunities.

### Applicant Management

The documented workflow allows institutions to review applicants, organize applicants in relation to jobs, and accept or reject candidates.

### Messaging

Institutions can initiate messaging with candidates as part of the recruitment workflow.

## 5. Role-Specific Navigation

After onboarding, the application reads the user's role and presents the appropriate post-login interface.

The job seeker interface includes dashboard, jobs, notifications, messages, and profile sections.

The hiring institution interface includes its dashboard, job-posting workflow, messaging, and other institution-specific sections.

## 6. Feature Scope and Verification

This document reflects the features and workflows described in the project's specifications.

It is intended to explain the system's scope rather than claim that every workflow has been independently tested or is operating without limitations.

Feature behavior, availability, and implementation details should be verified against the current application before this document is treated as a complete functional specification.

