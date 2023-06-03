# Containerized Infrastructure For Automated Testing
  <p align="left">
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/python.svg" title="Python" width="50" height="50"  alt="python"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/selenoid.svg" title="selenoid" width="50" height="50"  alt="selenoid"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/jenkins.svg" title="Jenkins" width="50" height="50"  alt="jenkins"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/allure.svg" title="Allure" width="50" height="50"  alt="allure"/>
 </p>

## Summary
This project is a result of an effort to learn how to setup ci for automation and make a template for personal automation development projects. It contains Jenkins, in which python is built-in in order to be able to run python tests on Jenkins' master machine and avoid setting up agents(TODO: Setup a few agents). These test runs will be executed in selenoid and logged as video, screenshot, html-page in an allure-report and linked to Jenkins' pipeline execution. There's also a selenoid-ui, which you can use for monitoring test runs, debugging them or just do manual testing if you'd like.

## Setup
- Make sure docker is installed on your machine
- Make sure that docker compose v2 is enabled

1. Pull the project to your desired directory using. It will take a few minutes, since jenkins and it's pluggins are already preinstalled
   ```
   git clone https://github.com/Fatalwgx/cvwebsite-infra-docker-jenkins-selenoid.git
   ``` 

2. Pull browser images for selenoid
   ```
   docker pull selenoid/chrome:112.0
   ```
3. Start services by running the following from project root
   ```
   docker compose up --build
   ```
