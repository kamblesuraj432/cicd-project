# cicd-project
# The steps to build and run the Docker container locally.
---- docker build -t kamblesuraj432/webapp .
     docker login -u kamblesuraj432 -p dckr_pat_mvMwzXSRGgFCiH9YNsPBoZc4zV4
     docker push kamblesuraj432/webapp

# How the CI/CD pipeline works and how to trigger it.
name: Docker Image CI

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3

    - name: Build the Docker image
      run: |
        docker build -t kamblesuraj432/webapp .
        docker login -u kamblesuraj432 -p dckr_pat_mvMwzXSRGgFCiH9YNsPBoZc4zV4
        docker push kamblesuraj432/webapp
