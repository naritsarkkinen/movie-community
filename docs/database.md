
# Database Design

The application uses PostgreSQL to store user information, movie reviews, lists, clubs, memberships, and messages.

Movie details are retrieved from the TMDB API using movie IDs.

## Entity Relationship Diagram

```mermaid
erDiagram
    USERS ||--o{ REVIEWS : writes
    USERS |o--o{ LISTS : owns
    USERS ||--o{ CLUB_MEMBERS : joins
    USERS ||--o{ CLUB_MESSAGES : sends

    LISTS ||--o{ LIST_ITEMS : contains

    CLUBS ||--o{ CLUB_MEMBERS : has
    CLUBS |o--o{ LISTS : owns
    CLUBS ||--o{ CLUB_MESSAGES : contains

    USERS {
        int user_id PK
        string nickname
        string email UK
        string password_hash
        timestamp created_at
    }

    REVIEWS {
        int review_id PK
        int user_id FK
        int tmdb_movie_id
        int stars
        string comment
        string visibility
        timestamp created_at
    }

    LISTS {
        int list_id PK
        int user_id FK
        int club_id FK
        string type
    }

    LIST_ITEMS {
        int list_id PK,FK
        int tmdb_movie_id PK
    }

    CLUBS {
        int club_id PK
        string name
        boolean is_public
    }

    CLUB_MEMBERS {
        int club_id PK,FK
        int user_id PK,FK
        string role
        string membership_status
    }

    CLUB_MESSAGES {
        int message_id PK
        int club_id FK
        int user_id FK
        string content
        timestamp created_at
    }
```

## Database Notes

- Each review belongs to one user and references a TMDB movie.
- Reviews can be public or private.
- Movie lists can belong to either a user or a club.
- Each list belongs to exactly one owner: a user or a club.
- Club memberships store user roles and membership status.
- Club messages belong to a club and have an author.
- Movie information is retrieved from TMDB instead of being stored in a separate movies table.

## Constraints

- User emails must be unique.
- Review stars must be between 1 and 5.
- Review visibility must be either public or private.
- A list must have exactly one owner (`user_id` or `club_id`).
- Primary and foreign keys must be enforced in PostgreSQL.

## Status

Reviewed and approved by the team.
