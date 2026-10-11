# Flask Portfolio — Jenkins CI/CD Project

A simple, responsive personal portfolio built with **Python, Flask, HTML, and CSS**.

This project serves as a hands-on DevOps practice environment for implementing a CI/CD pipeline using Jenkins and Docker. The goal is to automate the process of building, testing, and deploying a containerized Flask application.

## Features

- Single-page personal portfolio
- Responsive dark-themed interface
- About Me, Technical Skills, and Contact sections
- Flask-powered backend
- Docker containerization
- Jenkins CI/CD integration
- Docker image publishing to a container registry

## Tech Stack

- **Python & Flask** — Web application
- **HTML & CSS** — Frontend interface
- **Git & GitHub** — Source code management
- **Docker** — Application containerization
- **Jenkins** — CI/CD automation
- **Ubuntu WSL** — Local development environment

## Project Structure

```text
flask-portfolio/
├── app.py
├── Dockerfile
├── Jenkinsfile
├── requirements.txt
├── README.md
├── static/
│   └── style.css
└── templates/
    └── index.html
```

## Running the Application Locally

Install the Python dependencies:

```bash
pip install -r requirements.txt
```

Start the Flask application:

```bash
python3 app.py
```

Access the application at:

http://localhost:5000

## Running with Docker

Build the Docker image:

```bash
docker build -t flask-portfolio .
```

Run the application container:

```bash
docker run -d --name flask-portfolio -p 5000:5000 flask-portfolio
```

Access the application at:

http://localhost:5000

To stop the container:

```bash
docker stop flask-portfolio
```

## Jenkins CI/CD Pipeline

The project is intended to demonstrate an automated CI/CD workflow using Jenkins.

The planned pipeline includes:

1. **Source Checkout** — Retrieve application code from GitHub.
2. **Build** — Build the Flask application's Docker image.
3. **Test** — Execute application validation checks.
4. **Push** — Publish the Docker image to a container registry.
5. **Deploy** — Deploy the application to the configured environment.

Jenkins runs locally in a Docker container, while Docker is used to package and run the Flask application.

Pipeline implementation and deployment results will be documented after verification.

## Author

**Adeyeye Boluwatife**

DevOps & Backend Engineering Enthusiast

- GitHub: https://github.com/majortife
- LinkedIn: Adeyeye Boluwatife

## Acknowledgements

This project was adapted from the [Flask Portfolio repository](https://github.com/theshubhamgour/flask-portfolio) by Shubham Gour Tech.

The original application was simplified and personalized for hands-on Jenkins, Docker, and CI/CD practice.

## License

Refer to the original repository's license and attribution requirements.