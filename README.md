# InsightsAPP

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Node.js](https://img.shields.io/badge/node-v14.17.0-green.svg)
![Express](https://img.shields.io/badge/express-v4.17.1-green.svg)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-13.3-blue.svg)
![Sequelize](https://img.shields.io/badge/Sequelize-6.6.5-blue.svg)
![Redis](https://img.shields.io/badge/Redis-6.2.5-orange.svg)

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Configuration](#configuration)
  - [Database Setup](#database-setup)
  - [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [Testing](#testing)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

 <div align="center">
  <a href="https://cs-insights.uni-goettingen.de">
    <img src="images/Color logo - no background.png" alt="Logo" width="500">
  </a>
  <br />
  <br />
  <a href="http://cs-insights.uni-goettingen.de/">View Demo</a>
  </div>

## Introduction


**InsightsApp** is a powerful analytics tool designed to deliver comprehensive insights and analytics across various data sources, with a specialized focus on Semantic Scholars. Built with a modular architecture, InsightsApp ensures easy integration and scalability, allowing users to extend functionalities seamlessly to meet diverse analytical needs.

The backend is implemented as a robust RESTful API using **Node.js** and **PostgreSQL**, providing a scalable infrastructure for efficient data processing, storage, and retrieval. On the frontend, **Next.js**, a popular React framework, powers rich visualizations and interactive interfaces, offering users a fast and responsive experience to explore and analyze data effectively.

With InsightsApp, researchers, scientists, and data enthusiasts can extract valuable insights from Semantic Scholars data, visualize trends and patterns, and make informed, data-driven decisions. Whether it's analyzing research papers, exploring citation networks, or tracking the impact of scientific publications, InsightsApp serves as a comprehensive solution for data analysis and visualization.

By combining modular architecture, a robust RESTful API, efficient PostgreSQL database management, and advanced frontend technologies, InsightsApp empowers users to unlock the full potential of Semantic Scholars data, facilitating impactful projects and research endeavors.

## Features

- **Advanced Filtering**: Filter data based on year ranges, authors, venues, publication types, open access status, publishers, and citation counts.
- **Pagination and Ranking**: Efficiently navigate through large datasets with pagination and retrieve top-ranked records using window functions.
- **Caching with Redis**: Enhance performance by caching frequent queries and reducing database load.
- **Robust Error Handling**: Comprehensive error handling to ensure reliability and ease of debugging.
- **Logging**: Structured logging using Winston and Morgan for monitoring and debugging purposes.
- **API Documentation**: Well-documented API endpoints for seamless integration and usage.

## Technologies Used

- **Node.js**: JavaScript runtime environment for building scalable network applications.
- **Express.js**: Fast, unopinionated, minimalist web framework for Node.js.
- **TypeScript**: Typed superset of JavaScript that compiles to plain JavaScript.
- **PostgreSQL**: Powerful, open-source object-relational database system.
- **Sequelize ORM**: Promise-based Node.js ORM for PostgreSQL, MySQL, MariaDB, SQLite, and Microsoft SQL Server.
- **Redis**: In-memory data structure store, used as a database, cache, and message broker.
- **dotenv**: Module to load environment variables from a `.env` file into `process.env`.

## Dataset

InsightsAPP utilizes a comprehensive dataset of academic papers, encapsulated within the `papers` table in PostgreSQL. The dataset includes, but is not limited to, the following fields:

- **id**: UUID - Primary key.
- **publicationvenueid**: UUID - Identifier for the publication venue.
- **venue**: STRING - Name of the publication venue.
- **citationcount**: INTEGER - Number of citations the paper has received.
- **authors**: JSONB - Array of author objects containing details like `authorId`.
- **s2fieldsofstudy**: JSONB - Array of field of study objects containing categories.
- **year**: INTEGER - Year of publication.
- **openAccess**: BOOLEAN - Indicates if the paper is open access.
- **publicationtypes**: ARRAY of STRING - Types/categories of the publication.
- **publisher**: STRING - Name of the publisher.

**Note**: Ensure that the dataset is preprocessed and loaded into the PostgreSQL database before running the application.

## Getting Started

Follow these steps to set up and run InsightsAPP locally.

### Prerequisites

- **Node.js** (v14.17.0 or later)
- **npm** (v6.14.13 or later)
- **PostgreSQL** (v13.3 or later)
- **Redis** (v6.2 or later) - Optional, for caching
- **Git** - To clone the repository

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/muhammadtalha242/insightsApp.git
   cd insightsApp
   ```

2. **Install Dependencies**

   ```bash
   npm install
   ```

### Configuration

1. **Environment Variables**

   Create a `.env` file in the root directory and configure the following variables:

   ```env
   DB_HOST=localhost
   DB_NAME=your_db_name
   DB_USERNAME=your_db_user
   DB_PORT=5432
   DB_PASSWORD=your_db_password
   POSTGRES_HOST=localhost
   POSTGRES_USER=your_db_user
   POSTGRES_PASSWORD=your_db_password
   POSTGRES_DB=your_db_name
   REDIS_HOST=localhost
   REDIS_PORT=6379
   REDIS_PASSWORD=your_redis_password # If applicable
   ```

   **Note**: Replace `your_db_name`, `your_db_user`, `your_db_password`, and `your_redis_password` with your actual credentials.

### Database Setup

1. **Create PostgreSQL Database**

   Ensure PostgreSQL is running. Then, create a new database:

   ```bash
   psql -U your_db_user
   ```

   In the PostgreSQL shell:

   ```sql
   CREATE DATABASE your_db_name;
   \c your_db_name
   ```

2. **Run Migrations**

   Migrations set up the necessary tables and indexes.

   ```bash
   npx sequelize-cli db:migrate
   ```

   **Note**: Ensure that your `sequelize` configuration is correctly set in `config/config.js` or `config/config.ts` based on your project setup.

3. **Seed the Database (If Applicable)**

   If there are seed files to populate the database with initial data:

   ```bash
   npx sequelize-cli db:seed:all
   ```

### Running the Application

Start the server in development mode with hot-reloading:

```bash
npm run dev
```

Or, start the server in production mode:

```bash
npm start
```

The server should be running on `http://localhost:8000` (or the port specified in your `.env` file).

## Contributing

Contributions are welcome! Follow these steps to contribute to InsightsAPP:

1. **Fork the Repository**

   Click the [Fork](https://github.com/muhammadtalha242/insightsApp/fork) button at the top-right corner of this page.

2. **Clone Your Fork**

   ```bash
   git clone https://github.com/your_username/insightsApp.git
   cd insightsApp
   ```

3. **Create a New Branch**

   ```bash
   git checkout -b feature/YourFeatureName
   ```

4. **Make Changes and Commit**

   ```bash
   git commit -m "Add your detailed description here"
   ```

5. **Push to Your Fork**

   ```bash
   git push origin feature/YourFeatureName
   ```

6. **Create a Pull Request**

   Navigate to the original repository and click on the "Compare & pull request" button.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions or feedback, please contact:

- **Muhammad Talha**
- **Email**: [muhammadtalha242@example.com](mailto:muhammadtalha242@example.com)
- **GitHub**: [muhammadtalha242](https://github.com/muhammadtalha242)
