# Containerized Infrastructure For Automated Testing
  <p align="left">
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/python.svg" title="Python" width="50" height="50"  alt="python"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/selenoid.svg" title="selenoid" width="50" height="50"  alt="selenoid"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/jenkins.svg" title="Jenkins" width="50" height="50"  alt="jenkins"/>
    <img src="https://github.com/Fatalwgx/README/blob/master/icons/allure.svg" title="Allure" width="50" height="50"  alt="allure"/>
    <img src="https://cdn4.iconfinder.com/data/icons/logos-and-brands/512/97_Docker_logo_logos-256.png" title="Allure" width="50" height="50"  alt="allure"/>
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

## Misc

- From your host machine services will be available at locahost+port, but if you want your containers to communicate with eachother, keep in mind that, they need to be in the same network and insted of locahost url, they would use container_name as alias. For example to communicate with selenoid another container would need to reach to "selenoid:4444"
- It was intended to have Jenkins preconfigured, so there would be no need to setup plugins and pipeline. If you need, you can just drop jenkins' folder and reconfigure it from scratch. There should be first setup unstructions in jenkins' terminal
- Setup steps were written and tested on WSL2 configuration, so proper Linux environment might encounter some problems, but technically it shouldn't and I have no way to check as of this moment. If you've tried it on linux and whether or not you've encountred any problems - somekind of feedback would be appreciated.
