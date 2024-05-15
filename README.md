# InsightsApp

[![License](https://img.shields.io/github/license/muhammadtalha242/insightsApp)](LICENSE)
[![Build Status](https://img.shields.io/github/actions/workflow/status/muhammadtalha242/insightsApp/build.yml)](https://github.com/muhammadtalha242/insightsApp/actions)
[![Coverage Status](https://img.shields.io/codecov/c/github/muhammadtalha242/insightsApp)](https://codecov.io/gh/muhammadtalha242/insightsApp)

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
  - [Running the Application](#running-the-application)
- [Submodules](#submodules)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Introduction

InsightsApp is a powerful tool designed to provide comprehensive insights and analytics for various data sources. It is built with a modular architecture to allow easy integration and extension of functionalities.

## Features

- **Modular Architecture**: Easily extend and integrate new modules.
- **Data Visualization**: Comprehensive and interactive data visualization.

## Getting Started

Follow these instructions to set up and run the project on your local machine.

### Prerequisites

- Node.js 14+
- Docker

### Installation

1. **Clone the Repository**

    ```bash
    git clone --recurse-submodules https://github.com/muhammadtalha242/insightsApp.git
    cd insightsApp
    ```

### Running the Application

1. **Set Up Environment Variables**

    Create a `.env` file in the `csinsight_backend` directory by copying the `.env.example` file and updating the values according to your environment.

2. **Start the Application**

    Run the following command to start the application using Docker containers:

    ```bash
    docker-compose up
    ```

    This will build and start the backend and frontend services defined in the `docker-compose.yml` file.

3. **Access the Application**

    Once the application is running, open your browser and navigate to `http://localhost:3000` to access the frontend interface. From there, you can explore the various features and functionalities of the InsightsApp.

- **backend**: Contains the Node backend code.
- **frontend**: Contains the Nextjs frontend code.

Each submodule has its own README file with specific instructions on how to set up and use the submodule.

## Usage

Once the application is running, open your browser and navigate to `http://localhost:3000` to access the frontend interface. From there, you can explore the various features and functionalities of the InsightsApp.

## Contributing

Contributions are welcome! Please follow these steps to contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add your message'`).
5. Push to the branch (`git push origin feature/your-feature`).
6. Open a Pull Request.

Please make sure to update tests as appropriate.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

- [Next.js](https://nextjs.org/)
- [React](https://reactjs.org/)
- [Node.js](https://nodejs.org/)
- [Material-UI](https://material-ui.com/)
