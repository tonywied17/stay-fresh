# Week 4 Study Guide

## Day 1

What is a URL?

What is the difference between URL, URI, and URN?

What is client-server communication?

What is a web client? What is a web server?

What does it mean for a server to be stateless?

What is HTTP?

How is HTTP a form of client-server communication?

Do requests come from the client or the server? What about responses?

Determine whether requests, responses, or both have each of the following:
- headers
- body
- status code
- verb/method
- HTTP version
- URI

What are the 5 levels of status codes? What does each one mean?

What are some ways of sending HTTP requests?

What is Apache Tomcat?

What is a web/servlet container?

What is a Servlet?

Describe the Servlet inheritance hierarchy.

What is the servlet lifecycle?

What is a deployment descriptor?

How do we create our own servlet?

What is the servlet context?

What is the servlet config?

## Day 2

What are some methods we can use in an HttpServlet?

How do we get the request body in a servlet handler method?

How do we get request/query parameters?

How do we get request headers?

How do we set the response body for our servlet to send back?

How do we set response headers?

What is the RequestDispatcher?

What is the difference between redirects and forwards?

What is JSON?

Write this XML object as a JSON object:
``` xml
<User>
    <id>1</id>
    <username>testuser</username>
    <password>pass</password>
    <pets>
        <Pet>
            <id>1</id>
            <name>Fluffy</name>
        </Pet>
        <Pet>
            <id>2</id>
            <name>Rocky</name>
        </Pet>
    </pets>
</User>
```

What does the HttpSession object do?

How does the HttpSession make a server stateful?

What are some HttpSession methods?

What is the Front Controller Design Pattern?

What is the benefit of the FC design pattern?

What are JSON web tokens (JWTs)?

## Day 3

What is AWS EC2?

What is the benefit of using EC2 rather than an on premises server?

What command can you use to SSH into an EC2?

What is an AMI?

What is EBS?

What is autoscaling?

What is the difference between vertical and horizontal scaling?

Why might you prefer one or the other?

What is AWS Elastic Beanstalk?

What is AWS S3?

What is an S3 bucket?

What are objects in S3?

What can you use S3 for?

What are IaaS, PaaS, and SaaS? Give some examples of each.

## Day 4

What is DevOps?

What are the benefits of DevOps?

What are the downsides?

What is continuous integration?

What is continuous delivery?

What is continuous deployment?

When might you prefer continuous delivery vs. continuous deployment?

What is meant by the term "CI/CD pipeline"?

What is SonarCloud?

What are code smells?

Give an example of a code smell you might find in your code.

## Day 5

What is AWS CloudWatch?

What is infrastructure as code?

What are some IaC tools?

What is AWS CloudFormation?

What is containerization?

What is a container?

What is the difference between a container and a VM?

What is Docker?

What is the Docker daemon?

What are Docker images?

What is the difference between a Docker image and a Docker container?

Explain the following Docker commands:
- `docker container ls`
- `docker attach`
- `docker kill`
- `docker help`
- `docker inspect`

Explain the following Dockerfile keywords:
- `FROM`
- `COPY`
- `ADD`
- `WORKDIR`
- `ENV`
- `CMD`
- `RUN`

What is Docker compose? Why is it useful?

What are Docker volumes?

What is container orchestration?

What are some orchestration tools?