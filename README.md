# Java Web Application CI/CD Pipeline Using Jenkins (Windows Environment)

This project demonstrates a complete CI/CD pipeline for automating the build, test, and deployment process of a Java web application using Jenkins, Ant, JUnit, Tomcat, and GitHub — entirely on a Windows environment.

---

## 🚀 Tech Stack Used

- **Java (JDK 21)**
- **Apache Ant** – Build tool for generating WAR file  
- **JUnit** – Unit testing framework  
- **Apache Tomcat 9** – Deployment server  
- **Git & GitHub** – Source code management  
- **Jenkins** – CI/CD automation  

---

## 📂 Project Structure

The Java project contains a `pom.xml` and a standard Ant `build.xml` file used to compile and package the application into a `.war` file.

---

## 📌 Jenkins CI/CD Pipeline Overview

The pipeline consists of **four connected Jenkins jobs**, each with a specific responsibility.

### ### 1️⃣ First Job – Source Code Checkout
- Pulls code automatically from GitHub repository  
- Uses **Poll SCM** to trigger builds on code changes  
- Cleans workspace and fetches latest commit

### 2️⃣ Second Job – Build & Quality Check
- Runs Ant build commands  
- Compiles Java source files  
- Creates output directory and generates the **WAR file**  
- Performs basic quality checks

### 3️⃣ Third Job – Testing (JUnit)
- Executes JUnit test cases  
- Fails the job automatically if any test case fails  
- Publishes JUnit test results in Jenkins dashboard

### 4️⃣ Fourth Job – Deployment to Tomcat
- Deploys the generated WAR file to a local Tomcat server  
- Uses the Jenkins **Deploy to Container** plugin  
- Tomcat Manager credentials are configured in Jenkins  
- WAR deployed using the Tomcat Manager `/manager/html` API

---

## 🔄 Job Chaining (Build Flow)

The jobs run in sequence: 
GitHub → FirstJob → SecondJob → ThirdJob → FourthJob → Tomcat

- If any job fails, the pipeline stops.
- If all jobs succeed, the updated web application is deployed to Tomcat.

---
## ⚙️ Windows Environment Setup

### Software Installed
- Java JDK  
- Apache Ant  
- Apache Tomcat  
- Git for Windows  
- Jenkins (Windows Installer)

### Environment Variables Set

JAVA_HOME
ANT_HOME
CATALINA_HOME
PATH (added git, ant, java)


---

## ✔ Final Output

A fully automated CI/CD pipeline that:

1. Downloads latest code  
2. Builds WAR file  
3. Runs tests  
4. Deploys to Tomcat  

All with **one pipeline execution**.

---

## 📎 Screenshots (Optional)
- Jenkins Jobs
- <img width="1366" height="541" alt="1_jenkins" src="https://github.com/user-attachments/assets/b74ac009-3f00-4be0-b169-1f140132d8ea" />

- Build History
- <img width="1366" height="475" alt="2_build_pipeline" src="https://github.com/user-attachments/assets/d7d16531-2a2d-46fa-93c3-dcb1abde512c" />

  
- JUnit Reports
- <img width="1366" height="531" alt="3_deliver_pipeline" src="https://github.com/user-attachments/assets/ddef670d-c30a-449a-9777-ad66f3202125" />

- Tomcat Deployment Status
- <img width="1398" height="620" alt="4_build_war_file" src="https://github.com/user-attachments/assets/32976a7b-d833-4bcf-aa72-605c10d4ac26" />


---

## 🤝 Contributions
Feel free to fork this project and improve it!

---


##  CICD Pipeline

                 +-----------------------+
                 |     GitHub Repo       |
                 |  (SampleWebApp.git)   |
                 +-----------+-----------+
                             |
                             | Poll SCM
                             v
                 +-----------------------+
                 |     Jenkins Job 1     |
                 |     FIRSTJOB          |
                 |  Clone from GitHub    |
                 +-----------+-----------+
                             |
                             | Trigger
                             v
                 +-----------------------+
                 |     Jenkins Job 2     |
                 |     SECONDJOB         |
                 | Build .war via ANT    |
                 +-----------+-----------+
                             |
                             | Trigger
                             v
                 +-----------------------+
                 |     Jenkins Job 3     |
                 |      THIRDJOB         |
                 |  Run JUnit tests      |
                 +-----------+-----------+
                             |
                             | Trigger
                             v
                 +-----------------------+
                 |     Jenkins Job 4     |
                 |     FORTHJOB          |
                 | Deploy WAR to Tomcat  |
                 +-----------+-----------+
                             |
                             v
                 +-----------------------+
                 |    Apache Tomcat      |
                 |   Running WAR App     |
                 +-----------------------+



## 📬 Contact
For queries, reach out on LinkedIn 😊












