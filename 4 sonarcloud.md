# SonarCloud with AWS CodeBuild

## CI Pipeline with SonarCloud

1. make sure that your project is pushed to your github repository.
2. go to your repository page on github.
3. go to [sonarcloud](https://sonarcloud.io).
4. log in with github.
5. click the "+" at the top of the screen, then click "Analyze new project".
6. in the drop down, choose "220620-java".
7. find and select your project 1 repository/ies, then click "Set Up" in the box on the right.
8. on the next page, it may do automatic analysis. Wait for it to complete, then click Main Branch.
9. in the light blue text box, click "Setup CI-based analysis" then choose "With other CI tools".
10. choose "Maven".
11. scroll down and make sure you click the slider to turn off Automatic Analysis.
12. copy and paste the specified properties into your project's pom.xml.
13. open your CodeBuild project and choose Environment under the Edit drop down.
14. add the `SONAR_TOKEN` environment variable specified on SonarCloud and save the changes.
15. now, choose Buildspec under the Edit drop down and paste the Maven command specified by SonarCloud under commands. you can replace the other maven commands or you can leave them. remember that if you have more than one they should have the `&&` between them.
    - personally, i would keep mvn clean and mvn test.
16. save your changes, then click Start build or just push to your repository.
17. after it completes the build, SonarCloud should refresh and show you the updated results. if it doesn't just refresh it manually.