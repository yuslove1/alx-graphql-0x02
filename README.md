# alx-rick-and-morty-app: Querying the GraphQL Endpoint (alx-graphql-0x02)

This repository builds upon the project setup in `alx-graphql-0x01`, adding GraphQL queries to fetch data from the Rick and Morty API.

## Getting Started

1. **Clone the Repository:** `git clone https://github.com/yuslove1/alx-graphql-0x02.git`
2. **Navigate to Project Directory:** `cd alx-rick-and-morty-app`
3. **Install Dependencies:** `npm install` (or `yarn install`)
4. **Run the Development Server:** `npm run dev`


## GraphQL Integration

This project uses GraphQL to fetch data from the Rick and Morty API. The `utils/graphql-client.ts` file (or similar) contains the GraphQL client configuration.  Example queries are demonstrated below.


### Querying Episodes

The following query fetches data about episodes:

```typescript
import { gql } from '@apollo/client'; // Or your chosen GraphQL client library

const GET_EPISODES = gql`
  query GetEpisodes($page: Int) {
    episodes(page: $page) {
      info {
        count
        pages
      }
      results {
        id
        name
        air_date
        episode
      }
    }
  }
`;

// Example usage in a component:

// ... (Component code)

const { loading, error, data } = useQuery(GET_EPISODES, {
  variables: { page: 1 },
});

if (loading) return <p>Loading...</p>;
if (error) return <p>Error : {error.message}</p>;


// ... (render the episode data)

```

## Key Improvements
**GraphQL Integration:** Added GraphQL queries to fetch episode data.
**Data Display:** Implemented components to display the fetched data using Tailwind CSS for styling.
