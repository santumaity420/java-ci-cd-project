
# Jenkins Job Setup

## Option A: Pipeline Job (recommended)
- Create a **Pipeline** job named `deploy-insured-assurance`.
- In the job config, set **Pipeline script from SCM** or paste `Jenkinsfile` below.

## Option B: Freestyle Job
- Use `Execute shell` build step to pull artifact from GitHub or artifact repository and deploy to Tomcat using `curl` to Tomcat Manager.

## Jenkins credentials
- Add global credentials for Tomcat manager if needed.
- Ensure the Jenkins user has permissions.
