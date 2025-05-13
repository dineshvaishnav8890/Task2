# 🚀 DevOps CI/CD Pipeline – Task 2 (Elevate Labs Internship)

Welcome! This project demonstrates a complete Continuous Integration and Continuous Deployment (CI/CD) pipeline using **Jenkins**, **Docker**, and **Python Flask**.  
It was created as part of **Task 2** for my **DevOps internship at Elevate Labs**.

The goal is to build, test, and deploy a Dockerized web application automatically whenever changes are pushed to the GitHub repository.

---

## 📌 What This Project Does

✅ Automates the build of a Docker image for a Flask app  
✅ Runs unit tests using `pytest` inside a clean Python environment  
✅ Deploys the app using Docker  
✅ All tasks are automated using **Jenkins pipelines**

> 📢 Final Web Output:  
> **"Hello Team This is My Second Task For Elevate Labs"**

---

## 🧰 Tools & Technologies Used

| Tool           | Purpose / Role                          |
|----------------|------------------------------------------|
| **Jenkins**     | Automate CI/CD stages (build, test, deploy) |
| **Docker**      | Containerize and run the Flask app       |
| **GitHub**      | Host source code and trigger pipeline    |
| **Python Flask**| Backend framework for web application    |
| **pytest**      | Run automated unit tests on the app      |

---

## 📁 Project Structure


myapp/
├── app.py # Main Flask app
├── test_app.py # Unit test using pytest
├── requirements.txt # Python dependencies
├── Dockerfile # Instructions to build the container
└── Jenkinsfile # Jenkins pipeline definition





## 🧪 How the Jenkins Pipeline Works

### 🔨 Stage 1: Build
- Builds a Docker image named `myapp` using the `Dockerfile`
- Ensures the app and dependencies are packaged correctly

### ✅ Stage 2: Test
- Spins up a clean Python environment inside a Docker container
- Installs dependencies from `requirements.txt`
- Runs `pytest` to validate the app's behavior

### 🚀 Stage 3: Deploy
- Runs the Docker container exposing port `5000`
- App is accessible at `http://localhost:5000` (or your server IP)

Each stage is run automatically by Jenkins upon any GitHub commit.

---

## 📥 How to Run Locally (Without Jenkins)

You can test everything on your local machine using Docker:

### 1️⃣ Clone This Repository
```bash
git clone https://github.com/your-username/myapp.git
cd myapp



2️⃣ Build Docker Image
docker build -t myapp .


3️⃣ Run the Container
docker run -d -p 5000:5000 myapp


4️⃣ Access the App
http://IP-Address:5000






