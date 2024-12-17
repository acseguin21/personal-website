# Personal Website with Analytics

Welcome to the **Personal Website with Analytics** repository. This project is a comprehensive web application designed to showcase a cybersecurity professional's portfolio while integrating robust analytics and security features. The application is built using Node.js, Express, PostgreSQL, and Docker, with a focus on security best practices.

## Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Architecture](#architecture)
4. [Installation](#installation)
5. [Configuration](#configuration)
6. [Usage](#usage)
7. [Security Considerations](#security-considerations)
8. [Development](#development)
9. [Deployment](#deployment)
10. [Troubleshooting](#troubleshooting)
11. [Contributing](#contributing)
12. [License](#license)

## Project Overview

This project serves as a personal portfolio website for a cybersecurity professional. It includes sections for showcasing skills, projects, and contact information. Additionally, it features an admin dashboard for monitoring website analytics, powered by Grafana and PostgreSQL.

## Features

- **Responsive Design**: The website is designed to be responsive and accessible on various devices.
- **Security Best Practices**: Implements security features such as CSRF protection, rate limiting, and secure session management.
- **Analytics Dashboard**: Provides detailed analytics using Grafana, allowing for monitoring of website traffic and user interactions.
- **Admin Authentication**: Secure login system for admin access to the dashboard.
- **Dockerized Setup**: Utilizes Docker and Docker Compose for easy setup and deployment.

## Architecture

The application is structured into several key components:

- **Frontend**: Built with HTML, CSS, and JavaScript, providing a user-friendly interface.
- **Backend**: Developed using Node.js and Express, handling server-side logic and API endpoints.
- **Database**: PostgreSQL is used for storing user data, session information, and analytics.
- **Reverse Proxy**: Nginx is configured as a reverse proxy to handle HTTPS and route traffic to the backend.
- **Analytics**: Grafana is used to visualize data and provide insights into website usage.

## Installation

### Prerequisites

- **Docker**: Ensure Docker is installed on your system.
- **Docker Compose**: Required for managing multi-container Docker applications.

### Steps

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/acseguin21/personal-website.git
   cd personal-website
   ```

2. **Environment Configuration**:
   - Copy the example environment file and update it with your credentials:
     ```bash
     cp .env.example .env
     ```

3. **Build and Start the Application**:
   - Use Docker Compose to build and start the application:
     ```bash
     docker-compose up --build
     ```

4. **Access the Application**:
   - Visit `http://localhost` in your web browser to view the website.
   - Access the admin dashboard at `http://localhost/admin`.

## Configuration

### Environment Variables

The application uses environment variables for configuration. Key variables include:

- **Database Configuration**:
  - `POSTGRES_USER`: Database username.
  - `POSTGRES_PASSWORD`: Database password.
  - `POSTGRES_DB`: Database name.

- **Session Management**:
  - `SESSION_SECRET`: Secret key for session encryption.

- **Admin Credentials**:
  - `ADMIN_USERNAME`: Admin username.
  - `ADMIN_PASSWORD`: Admin password.

- **Grafana Configuration**:
  - `GRAFANA_ADMIN_PASSWORD`: Password for Grafana admin user.

### Nginx Configuration

Nginx is configured to handle HTTPS and proxy requests to the backend. The configuration files are located in the `nginx` directory.

- **SSL Certificates**: Place your SSL certificates in the `nginx/ssl` directory.
- **Configuration Files**: Modify `nginx.conf` and `default.conf` as needed.

## Usage

### Admin Dashboard

The admin dashboard provides insights into website traffic and user interactions. It is accessible at `http://localhost/admin`.

- **Login**: Use the admin credentials specified in the `.env` file.
- **Analytics**: View detailed analytics via the Grafana dashboard at `http://localhost:3001`.

### Website Sections

- **Home**: Introduction and highlights of the professional's expertise.
- **About**: Detailed background and achievements.
- **Projects**: Showcase of key projects and contributions.
- **Contact**: Contact information and social media links.

## Security Considerations

Security is a top priority in this project. Key security features include:

- **CSRF Protection**: Implemented using the `csurf` middleware.
- **Rate Limiting**: Limits the number of requests to prevent abuse.
- **Secure Sessions**: Sessions are encrypted and stored securely.
- **Input Validation**: Ensures data integrity and prevents injection attacks.

## Development

### Local Development

For local development, you can run the application without Docker:

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Start the Server**:
   ```bash
   npm start
   ```

3. **Access the Application**:
   - Visit `http://localhost:3000` in your web browser.

### Code Structure

- **Frontend**: Located in the `static` directory, including CSS and JavaScript files.
- **Backend**: Main server logic is in `src/server.js`.
- **Database**: SQL initialization scripts are in the `db` directory.

## Deployment

### Production Deployment

For production deployment, ensure the following:

- **Environment Variables**: Set `NODE_ENV=production` for optimized performance.
- **SSL Certificates**: Use valid SSL certificates for HTTPS.
- **Secure Configuration**: Review and apply security best practices.

### Continuous Integration

Consider setting up CI/CD pipelines for automated testing and deployment.

## Troubleshooting

### Common Issues

- **Database Connection**: Ensure PostgreSQL is running and credentials are correct.
- **SSL Errors**: Verify SSL certificates are correctly configured.
- **Docker Issues**: Check Docker logs for detailed error messages.

### Logs

- **Nginx Logs**: Located in `nginx/logs`.
- **Application Logs**: Check console output for server logs.

## Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork the Repository**: Create a personal fork of the project.
2. **Create a Branch**: Use descriptive names for new branches.
3. **Submit a Pull Request**: Provide a detailed description of changes.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

This README provides a comprehensive overview of the Personal Website with Analytics project. For further assistance, please refer to the documentation or contact the project maintainers.
