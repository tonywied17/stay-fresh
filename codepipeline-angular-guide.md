# AWS CodePipeline Guide

*Last updated: 8/1/22*

This guide is for setting up a CI/CD pipeline with an Angular project. It will use GitHub for source, AWS CodeBuild for build, and AWS S3 for deploy.

1. Go to AWS CodePipeline and choose to create a new pipeline.
2. Give the pipeline a name and create a new service role.
    - This role is an IAM role. If you need to view/modify/delete it for any reason, you can find it in IAM.
    - If you *do* find that you need to change the role later, make sure that you don't update the default, as the pipeline cannot use the role if the default version is modified.
3. After giving the service role a name, everything else can remain default. Click Next.
4. Under Source provider, choose Github (version 2).
5. Under connection, click Connect to GitHub and set up a connection with the repository that you're working with.
6. Set the repository name and the branch you want to use in your pipeline (most likely `main`).
7. Everything else can remain default. Click Next.
8. Under Build provider, choose AWS CodeBuild.
9. Under Project name, click Create project to create the project on CodeBuild.
10. Give the project a name. You can have it match the pipeline name or make it something different.
11. Under Environment, choose Managed image and set the operating system to Amazon Linux 2.
12. Set Runtime to Standard, Image to the latest (4.0), and leave the rest default.
13. In Build specifications, you can leave everything default. You will need to create a buildspec.yml file in your repository at top level.
    - The `buildspec.yml` file is a configuration file for AWS CodeBuild that explains what the build steps are and any other relevant configuration. There is a guide for this [below](#buildspec-file).
14. You can leave everything else as the default and choose Continue to CodePipeline.
15. Back in CodePipeline, you can leave the environment variables blank since you set them in CodeBuild. If you didn't set them there, you can set them here, but it's unnecessary to set them twice.
16. Choose Single build and click Next.
17. Under Deploy provider, choose AWS S3.
18. Choose the bucket that you want to use. This should be an already existing bucket that is set up for hosting a static website ([check out this guide](https://docs.aws.amazon.com/AmazonS3/latest/userguide/HostingWebsiteOnS3Setup.html)).
    - **NOTE: make sure that the S3 bucket that you create is in the same AWS region as the pipeline.**
    - For an Angular application, you'll want to set both the default page and the error page to `index.html` in order for routing to work.
19. Check the box that says `Extract file before deploy` then click Next.
20. Review your choices, then click Create Pipeline. This will trigger an initial run through the pipeline to make sure that everything is working. 
    - Keep in mind that the Build step will be fairly slow; it typically takes several minutes as it needs to provision resources to run the build.

## Buildspec File

The `buildspec.yml` file is the configuration file that AWS CodeBuild uses in order to know what it's supposed to do during the build process. You can find the documentation [here](https://docs.aws.amazon.com/codebuild/latest/userguide/build-spec-ref.html).

Here is an example of the basic `buildspec.yml` configuration that you'll need for the guide above. Keep in mind that yml is a whitespace-based format, so each indent must be two spaces.

``` yml
version: 0.2

phases:
  install:
    commands:
      - curl -fsSL https://dev.nodesource.com/setup_16.x | sudo -E bash -
      - yum install gcc-c++ make
  pre_build:
    commands:
      - npm i -g @angular/cli
      - npm install --force
  build:
    commands:
      - ng build

artifacts:
  files:
    - "**/*"
  discard-paths: no
  base-directory: dist/pet-app-ng
```

There are three phases in this build: `install`, which installs Node.js, `pre_build`, which installs the Angular CLI and the node_modules for the project, and `build` which builds the application. After this, the artifacts are set as the output to the `dist` folder so that they can be found for the deploy step of the pipeline.