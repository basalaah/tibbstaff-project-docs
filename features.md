# Features and User Workflows

## 1. User Roles

The platform supports two primary user roles.

| Role | Description |
|---|---|
| Job Seeker (`باحث عن عمل`) | A healthcare professional exploring employment opportunities |
| Hiring Institution (`مؤسسة توظيف`) | An organization recruiting healthcare professionals |

The selected role determines the user's post-login experience and available navigation.

## 2. Authentication and Onboarding

The documented onboarding workflow is:

1. The user opens the application.
2. Unauthenticated users are directed to sign in.
3. After successful authentication, the application checks for a user profile.
4. If a profile is missing, the application creates one.
5. If the profile has no role, the user is directed to onboarding.
6. The user chooses Job Seeker or Hiring Institution.
7. The role is saved using `ProfileService.updateRole(role)`.
8. The application navigates to the post-login shell.
9. The shell reads the role and displays the appropriate user interface.

## 3. Job Seeker Experience

### 3.1 Dashboard

The job seeker dashboard includes summary cards that provide an overview of relevant activity.

The documented dashboard workflow includes access to:

- Invitations.
- Job applications.
- Saved jobs.
- Messages.

### 3.2 Invitations Inbox

Job seekers can access the invitations area to review invitations associated with their recruitment journey.

The precise invitation states and available actions should be verified against the current implementation.

### 3.3 Application Tracking

The application provides a workflow for job seekers to access and track their job applications.

The exact application statuses and transitions should be documented according to the implemented behavior.

### 3.4 Saved Jobs

Job seekers can save and unsave job listings and access their saved jobs through the application.

### 3.5 Job Browsing, Search, and Filtering

The jobs section provides access to job listings, search, and filtering functionality.

These features help job seekers discover opportunities relevant to their needs.

### 3.6 Job Applications

Job seekers can follow the job application workflow from available listings.

Access to job-related features is profile-gated. Users may need to satisfy the application's profile requirements before proceeding with relevant actions.

The exact profile requirements and validation rules should be verified before documenting them in detail.

### 3.7 Profile Access

Job seekers have access to their profile section, where they can review or manage their profile information according to the available functionality.

### 3.8 Messages

Job seekers can access conversations through the messaging interface.

The conversation system supports unread-message badge behavior and links to support conversations.

## 4. Hiring Institution Experience

### 4.1 Institution Dashboard

The institution dashboard provides an overview of recruitment activity and institution-related information.

Documented dashboard elements include:

- Profile completion.
- Verification status.
- Quick statistics.
- Access to jobs and applicants.

### 4.2 Job Posting

Hiring institutions have access to a job-posting workflow for publishing recruitment opportunities.

### 4.3 Applicants Grouped by Job

The institution workflow organizes applicants in relation to their associated jobs, allowing institutions to review candidates in the context of specific recruitment opportunities.

### 4.4 Candidate Actions

The documented candidate-management workflow includes accepting or rejecting candidates.

The precise status changes, permissions, and downstream effects should be verified against the implementation.

### 4.5 Conversation Initiation

Hiring institutions can initiate conversations with candidates through the messaging workflow.

### 4.6 Institution Profile and Verification Status

The institution dashboard displays profile-completion and verification-status information.

These indicators should be documented separately from applicant-document verification unless the implementation explicitly connects the two workflows.

## 5. Applicant Document Review and Verification Badge

The project includes a documented verification-related workflow involving the review of applicant documents and a verification badge.

The intended process is to review the relevant applicant documents and confirm that the required files are acceptable before granting the applicable verification status.

Before describing this as a fully operational feature, confirm:

- Who is authorized to review the documents.
- Which documents are required.
- Whether the review and approval process is implemented.
- What the badge represents and which user or profile displays it.
- How the status changes after approval or rejection.

Do not interpret a verification badge as proof of a person's professional license or credentials unless the actual verification process supports that claim.

## 6. Messaging and Conversations

The documented messaging functionality includes:

- A conversation tab or messaging entry point.
- Unread-message badge support.
- Deep links to support conversations.
- Conversation initiation from the hiring institution's candidate workflow.

The exact unread-count rules, message states, and supported deep-link behavior should be confirmed against the current implementation.

## 7. Notifications

The application has a unified alerts tab and notification badge behavior in its notification workflow.

The notification system is planned and partially wired up, with feature-flag-based rollout.

Accordingly, notification functionality should be described as partially implemented until the relevant flows have been tested and confirmed to work end to end.

The presence of a tab or badge does not by itself establish that every notification trigger, delivery path, or user interaction is fully operational.

## 8. Current Implementation Status

The project is live and has received user registrations, but overall traffic and adoption remain limited.

The feature descriptions in this document reflect the documented scope and workflows. Individual features should be verified against the current application before being represented as fully operational.

