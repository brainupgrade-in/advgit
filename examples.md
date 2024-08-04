# CODEOWNERS

https://github.com/brainupgrade-in/request-logger/blob/main/.github/CODEOWNERS
https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/CODEOWNERS
https://github.com/brainupgrade-in/weather-py/blob/main/.github/CODEOWNERS

./gitops/gitops-apps-hello/.github/CODEOWNERS
./github-workflows/.github/CODEOWNERS
https://github.com/ghewareunigpssolutions/codeowners/blob/main/.github/CODEOWNERS

# Github Actions

## simple matrix build:
https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/matrix.yml
# java maven build - simple workflow (push main):
https://github.com/brainupgrade-in/spring-petclinic/blob/main/.github/workflows/maven-build.yml (-Dcheckstyle.skip -DskipTests)
## Manual driven workflow:
https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/codeql.yml
## Call reusable workflow:
https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/call-maven-build-workflow.yaml

## cache and docker:
https://github.com/brainupgrade-in/request-logger/blob/main/.github/workflows/build-test-push.yml
## docker build push test (push pull main):
https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/ci.yml
## docker build and push (push tag):
https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/docker-publish.yml
## Release on tag (push tag):
https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/release-on-tag.yml


## matrix codeql (push pull main):
https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/codeql.yml
## callable workflow:
https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/maven-build.yml
## auto assign - PR, issue:
https://github.com/ghewareunigpssolutions/demo-repository/blob/main/.github/workflows/auto-assign.yml

## Github Pages
https://github.com/brainupgrade-in/weather-py/blob/main/.github/workflows/jekyll-gh-pages.yml

## create release (push tag ) (skip):
https://github.com/brainupgrade-in/gitops-apps-hello/blob/main/.github/workflows/release.yml
https://github.com/brainupgrade-in/github-workflows/blob/main/.github/workflows/release.yml 


## References
- workflow syntax:
https://docs.github.com/en/actions/using-workflows/workflow-syntax-for-github-actions
- Event Triggers:
https://docs.github.com/en/actions/using-workflows/events-that-trigger-workflows

- Runner images https://github.com/actions/runner-images/blob/ubuntu22/20240730.2/images/ubuntu/Ubuntu2404-Readme.md

- Example workflow https://docs.github.com/en/actions/examples/using-scripts-to-test-your-code-on-a-runner#example-workflow

# Codespaces - decontainers

https://github.com/brainupgrade-in/weather-py/tree/develop
https://github.com/brainupgrade-in/request-logger/tree/develop
https://github.com/brainupgrade-in/spring-petclinic/blob/main/.devcontainer/devcontainer.json

https://github.com/ghewareunigpssolutions/github-jenkinscicd/blob/main/.devcontainer/devcontainer.json
https://github.com/ghewareunigpssolutions/github-kind/blob/main/.devcontainer/devcontainer.json
https://github.com/ghewareunigpssolutions/github-kind/blob/main/.github/workflows/self-hosted-runner.yml
https://github.com/ghewareunigpssolutions/github-selfhostedrunner/blob/main/.github/workflows/build-runs-on-self-hosted-runner.yml

## Dev container ref:
features - https://github.com/devcontainers/features/tree/main/src
images - https://github.com/devcontainers/images/tree/main/src

# Misc
ghewareunigpssolutions/github-selfhostedrunner
github-copilot-demo
