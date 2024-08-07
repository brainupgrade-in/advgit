# CODEOWNERS

- https://github.com/brainupgrade-in/request-logger/blob/main/.github/CODEOWNERS
- https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/CODEOWNERS
- https://github.com/brainupgrade-in/weather-py/blob/main/.github/CODEOWNERS
- https://github.com/brainupgrade-in/gitops/gitops-apps-hello/.github/CODEOWNERS
- https://github.com/ghewareunigpssolutions/github-workflows/.github/CODEOWNERS
- https://github.com/ghewareunigpssolutions/codeowners/blob/main/.github/CODEOWNERS

# Github Actions

- Python -  build and test - https://github.com/brainupgrade-in/gh-actions-python/blob/main/.github/workflows/build-test.yml
- Simple matrix build -  https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/matrix.yml
- Manual driven workflow CodeQL on Java: https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/codeql.yml
- Use cache between docker steps: https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/build-test-push.yml
- Docker build & Test in Kubernetes cluster (push pull main): https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/ci.yml
- Docker build and push (PUSH on tag):https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/docker-publish.yml
- Create Github Release on tag (push tag): https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/release-on-tag.yml
- CodeQL - Go (push pull main): https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/codeql.yml
- Call reusable workflow: https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/call-maven-build-workflow.yaml
- Callable / reusable workflow java maven build - simple workflow (push main) https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/maven-build-reusable.yml (-Dcheckstyle.skip -DskipTests)

- auto assign - PR, issue: https://github.com/ghewareunigpssolutions/demo-repository/blob/main/.github/workflows/auto-assign.yml
- Github Pages https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/jekyll-gh-pages.yml
- create release (push tag ) (skip): https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/release.yml
https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/release.yml 


# Codespaces - decontainers
- Simple / Default https://github.com/brainupgrade-in/gh-actions-python
- Python https://github.com/brainupgrade-in/weather-py/tree/develop
- Java Spring boot https://github.com/brainupgrade-in/request-logger/tree/develop
- Java Spring Boot https://github.com/brainupgrade-in/spring-petclinic/blob/main/.devcontainer/devcontainer.json

- OSS Jenkins https://github.com/ghewareunigpssolutions/github-jenkinscicd/blob/main/.devcontainer/devcontainer.json
- OSS Kubernetes https://github.com/ghewareunigpssolutions/github-kind/blob/main/.devcontainer/devcontainer.json
- Self Hosted Runner - Simple: https://github.com/ghewareunigpssolutions/github-kind/blob/main/.github/workflows/self-hosted-runner.yml
- Self hosted runner - EC2 deploy:  https://github.com/ghewareunigpssolutions/github-selfhostedrunner/blob/main/.github/workflows/build-runs-on-self-hosted-runner.yml

# References
- Workflow syntax: https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions
- Event Triggers: https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows
- Runner Images https://github.com/actions/runner-images/blob/ubuntu22/20240730.2/images/ubuntu/Ubuntu2404-Readme.md
- Example GH Actions Workflow https://docs.github.com/en/actions/examples/using-scripts-to-test-your-code-on-a-runner#example-workflow
- Devcontainer Features - https://github.com/devcontainers/features/tree/main/src
- Devcontainer Images - https://github.com/devcontainers/images/tree/main/src

# Misc
github-copilot-demo
