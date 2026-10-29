
# System Architecture

The application uses a React frontend, an Express REST API backend, and a PostgreSQL database. Movie information is retrieved from the external TMDB API.

## Architecture Diagram

```mermaid
flowchart LR
    User["User Browser"]

    subgraph Frontend["Frontend"]
        React["React SPA"]
    end

    subgraph Backend["Backend"]
        Express["Express REST API"]
    end

    subgraph Database["Database"]
        PostgreSQL[("PostgreSQL")]
    end

    subgraph ExternalServices["External Services"]
        TMDB["TMDB API"]
    end

    User -->|Interacts with| React
    React -->|HTTPS / JSON REST| Express
    Express -->|SQL Queries| PostgreSQL
    Express -->|HTTPS / JSON| TMDB
```

## Components

- **React:** User interface and client-side navigation.
- **Express:** REST API, authentication, and application logic.
- **PostgreSQL:** Stores users, reviews, movie lists, and clubs.
- **TMDB API:** Provides movie information.
