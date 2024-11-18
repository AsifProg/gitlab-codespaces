# gitlab-codespaces
Lab 2: Installing GitLab on GitHub Codespaces and Setting Up CI/CD
Objective:
The primary goal of Lab 2 was to install GitLab on GitHub Codespaces, set it up as a DevOps tool, and build a basic CI/CD pipeline using GitLab's CI/CD features. This lab demonstrated GitLab's capabilities for managing repositories, automating workflows, and running tests within a unified development environment.
Steps completed: Setting up GitHub Codespaces:

I created a GitHub repository and launched Codespaces as the workspace.
I verified that the Docker engine was running for containerized services.
Installing GitLab.

I pulled the official GitLab Docker image and launched the container with the following command:
docker run --detach \
  --hostname gitlab.example.com \
  --publish 443:443 --publish 80:80 --publish 22:22 \
  --name gitlab \
  --restart always \
  gitlab/gitlab-ce:latest

Accessing GitLab.

GitLab was accessed in the browser using the configured domain and port (for example, http://localhost:80).
Logged in with root account credentials:
Username: root.
Password: Reset with the following commands:
docker exec -it gitlab gitlab-rails console
user = User.find_by(username: 'root')
user.password = 'new_password_here'
user.password_confirmation = 'new_password_here'
user.save!
Configuring GitLab.

GitLab's basic settings have been customized, including the domain name and SMTP for email notifications.
Investigated the Admin Dashboard to better understand system settings and user management.
Setting up CI/CD.

I created a new GitLab project by importing an existing GitHub repository.
Added the.gitlab-ci.yml file to define the CI/CD pipeline.
Running automation scripts

Configured the pipeline to run automation tests on LambdaTest with Python and Selenium.
Verified the pipeline logs to ensure the job was completed successfully.
Observing Pipeline Results.

I opened GitLab's CI/CD tab to view pipeline details and logs.
Debugging any issues that arose during pipeline execution ensures that all jobs run smoothly.
Documenting Progress

Created GitLab issues to document observations and challenges encountered.
I took screenshots throughout the process to document configurations, pipeline runs, and results.


