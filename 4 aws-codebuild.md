# Making a CI pipeline with AWS CodeBuild

1. go to CodeBuild on the AWS console.
2. create a new project.
3. give your project a name.
4. for the Source, choose GitHub as the source provider and add a personal access token. you could use yours or create a new one on GitHub for AWS to control its access.
5. choose Repository in my GitHub account and add your repository URL.
6. under Primary source webhook events, check the box for Rebuild every time a code change is pushed to this repository.
7. choose Single build and choose the event types you want to trigger builds with.
6. in environment, choose a managed image, Amazon Linux 2, Standard, and x86_64-standard:4.0. check the Privileged box so that you can build Docker images.
7. if you are using environment variables for your application's database info, click Additional configuration to set up the environment variables.
7. under Buildspec, choose Insert build commands and write the maven commands. if you are using environment variables for your database connection, you may also need to specify those.
``` sh
# if just maven
mvn clean && mvn test && mvn package
```
8. everything else can remain default, so go to the bottom and choose Create build project.
9. next, you should be on the build project page. in order to trigger a build, you can either push to your github repository or click Start build. the logs will tell you if anything went wrong along the way.
    - note: the build can be VERY slow. it might take a few minutes; that's normal.