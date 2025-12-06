
# Insured Assurance – CI/CD with GitHub Actions + Jenkins (Tomcat)

This sample repository demonstrates a CI/CD pipeline where **GitHub Actions** performs build/test (Maven)
and then **invokes a Jenkins job** to deploy a Java web application (WAR) to **Apache Tomcat**.

## Structure
```
InsuredAssurance_CICD/
├─ .github/workflows/maven.yml
├─ jenkins/Jenkinsfile
├─ jenkins/README.md
├─ app/pom.xml
├─ app/src/main/java/com/insured/assurance/App.java
├─ app/src/test/java/com/insured/assurance/AppTest.java
├─ app/src/main/webapp/WEB-INF/web.xml
├─ app/src/main/webapp/index.jsp
├─ docs/
│   ├─ screenshots/ (place your outputs here)
│   └─ tomcat-config.md
└─ .gitignore
```

## Prerequisites
- JDK 17 (or 11+) installed on runner/agents
- Maven 3.8+
- Jenkins reachable from GitHub Actions (public URL or via GitHub self-hosted runner in same network)
- Jenkins credentials set in GitHub **Repository → Settings → Secrets and variables → Actions**:
  - `JENKINS_URL` (e.g., https://jenkins.example.com)
  - `JENKINS_USER`
  - `JENKINS_API_TOKEN`
  - `JENKINS_JOB` (e.g., deploy-insured-assurance)

## Quick start
1. Push this folder as a Git repo.
2. In Jenkins, create a **Pipeline** job and point to `jenkins/Jenkinsfile` or use the freestyle job as per your setup.
3. Configure Tomcat manager credentials and deployment path (see `docs/tomcat-config.md`).
4. Commit and push; GitHub Actions will build & test, then trigger Jenkins to deploy.

## Notes
- The workflow is set to run on `push` to `main` and via manual `workflow_dispatch`.
- Adjust Java version and Maven cache as required.  
