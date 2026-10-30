# MovieBus – Requirements Specification

**Version:** 0.1 

**Status:** Pending customer approval


## 1. Project Overview

MovieBus is a web application for movie enthusiasts, with a focus on community features. Its purpose is to make it easier to discover movies, browse movie information, share reviews, and discuss movies with groups of friends.

According to the customer's initial requests:

- Visitors can browse movies, basic movie information, and public reviews without logging in.
- Users can search for movies and filter search results.
- Logged-in users can review movies.
- Users can create groups and participate in group discussions.
- The application must also be usable on mobile devices.
- The expected user base is approximately 2,000 users. This does not mean 2,000 concurrent users.


### 1.1 User Roles (Preliminary Interpretation)

- **Visitor:** Can browse movies, basic movie information, and public reviews.
- **Logged-in user:** Can post reviews and use community features as they become available.
- **Group member:** Can participate in the activities of their group.
- **Group administrator:** Can manage group memberships and content according to permissions to be agreed upon with the customer.

The exact permissions for each role will be clarified later.


## 2. Functional Requirements (FR)

The following requirements were included in the original preliminary requirements list. Their priorities and any further details must be confirmed with the customer.

| ID | Requirement |
| --- | --- |
| FR-01 | Users can browse movies and view their basic information without logging in. |
| FR-02 | Users can search for movies using a search feature. |
| FR-03 | Users can filter movie search results based on different criteria. |
| FR-04 | The system displays information about which movie theaters are showing a movie. |
| FR-05 | Logged-in users can rate movies on a scale of 1–5 stars. |
| FR-06 | Logged-in users can write text reviews of movies. |
| FR-07 | Registered users can create movie groups. |
| FR-08 | Group members can communicate with each other in a group discussion. |


### 2.1 Additional Features Requested by the Customer

The following features were mentioned during the customer's initial presentation but have not yet been formalized as individual functional requirements or prioritized:

- Featured or interesting movies and a search feature on the home page.
- Advanced search filters and potentially personalized movie recommendations.
- Movie screening information and key movie details.
- Public and private reviews, as well as review history.
- Group discovery, approval or rejection of join requests, member removal, and the ability to leave a group.
- Assigning or transferring group administrator permissions and moderating inappropriate content.
- Personal movie lists and group-specific lists, including sharing lists with people who are not logged in.
- Adding friends and viewing which groups they belong to.
- Group discussion functionality; whether real-time messaging is required remains to be clarified.
- Possible statistics about watched movies and other activity.
- A primarily Finnish-language interface, with possible support for English and Swedish.


## 3. Non-Functional Requirements (NFR)

| ID | Requirement | Verification Method |
| --- | --- | --- |
| NFR-01 | The website must work on both mobile devices and computers. | Test on different devices and screen sizes. |
| NFR-02 | The website must support a user base of approximately 2,000 users. More specific performance targets will be agreed upon later. | Perform load testing against agreed performance targets. |
| NFR-03 | Private content must be accessible only to authorized users. | Test user roles and access permissions. |
| NFR-04 | The user interface must be clear, consistent, and easy to use. | Conduct usability testing. |


## 4. Assumptions – Not Yet Approved Requirements

| ID | Assumption |
| --- | --- |
| A-01 | The first release can be used without registration, but community features will require a user account later. |
| A-02 | Basic movie information will be retrieved from an external movie database. |
| A-03 | Group discussions will only be visible to group members. |
| A-04 | Users can submit a star rating without writing a text review. |
| A-05 | Movie theater screening information will primarily cover theaters in Finland. |


## 5. Requirements Prioritization

| Requirement | Priority |
| --- | --- |
| FR-01 | Must Have |
| FR-02 | Must Have |
| FR-03 | Could have |
| FR-04 | Must have |
| FR-05 | Must have |
| FR-06 | Must have |
| FR-07 | Could have |
| FR-08 | Should have |


## 7. Approval and Change Management

- **Requirements approval:** Pending customer/supervisor approval.
- **Updates:** Requirements may be refined throughout the project.
- **Product Backlog:** Approved and prioritized requirements will be used to create Product Backlog items and User Stories in GitHub Projects.
- **Technical design:** Architecture, database design, and technology choices will be documented separately in the technical specification.
