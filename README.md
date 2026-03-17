# Code Snippets API

A RESTful API backend for a code snippets sharing platform. Users can create, search, filter, edit, and delete code snippets, as well as comment and vote on them.

## Features

- **CRUD Operations** -- Create, read, update, and delete code snippets
- **Search** -- Full-text search on snippet titles
- **Filter by Language** -- Retrieve snippets filtered by programming language
- **Filter by Tags** -- Retrieve snippets filtered by tags
- **Commenting** -- Add and manage comments on code snippets
- **Voting** -- Upvote/downvote code snippets
- **User Management** -- Basic user and admin role support
- **Multi-environment Config** -- Separate configurations for local, test, and production
- **Docker Support** -- Containerized deployment with Docker and Kubernetes manifests

## Tech Stack

- **Runtime:** Node.js
- **Framework:** Express.js
- **Database:** MongoDB (via Mongoose ODM)
- **Build Tool:** Gulp
- **Containerization:** Docker
- **Orchestration:** Kubernetes (deployment.yaml, service.yaml)
- **Other:** CORS, Morgan (logging), Body-Parser, Method-Override

## Setup / Installation

### Prerequisites

- Node.js (v10+)
- MongoDB instance (local or remote)

### Local Development

```bash
git clone https://github.com/bnarasimha21/code-snippets-api.git
cd code-snippets-api
npm install
```

Configure your MongoDB connection string in `config/config.local.js`, then start the server:

```bash
npm start
```

The API will be available at `http://localhost:4000`.

### Docker

```bash
docker build -t code-snippets-api .
docker run -p 4000:4000 code-snippets-api
```

## Usage

### API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/api/codeSnippets` | Get all code snippets (sorted by date) |
| GET | `/api/codeSnippets/:id` | Get a single code snippet by ID |
| GET | `/api/searchCodeSnippets/:searchText` | Search snippets by title |
| GET | `/api/CodeSnippets/language/:language` | Filter snippets by language |
| GET | `/api/CodeSnippets/tags/:tags` | Filter snippets by tag |
| POST | `/api/addCodeSnippet` | Add a new code snippet |
| POST | `/api/editCodeSnippet` | Update an existing code snippet |
| DELETE | `/api/deleteCodeSnippet/:id` | Delete a code snippet and its comments/votes |

## License

MIT
