
# BYOCM=BringYourOwnConfigurationManagement

## Requirements

Imagine you’re part of a team that is starting a blogging application that would eventually run on the cloud (let’s assume it's AWS). The team has decided to use Wordpress to get a simple blog running as a start. Your team of developers wants you to help them monitor their application and the computers their application are running on. Since cloud is the target infrastructure, you decide to collect metrics with Prometheus and cAdvisor and to visualise with Grafana. The entire infrastructure is intended to be a container based system. In order to achieve the above, you would need to:

Create a Docker compose based Prometheus setup, so that it's repeatable and demonstrable on a development machine.
Use a tool of choice for provisioning the minimal AWS infrastructure to run the the Wordpress and Prometheus.
Deploy dockerized WordPress based blogging application.
Monitor the AWS resources and the blogging application using Prometheus and Grafana.
For bonus points: Demonstrate your knowledge and understanding by preparing an insightful dashboard of your choice; importing dashboards from Grafana sources is absolutely fine.
To make things simple, you can use the official WordPress Docker image to run a web application and monitor it using Prometheus with EC2 discovery.

## Specification

- OS: Amazon Linux 2
- App Server: Gunicorn/Nginx/?
- Configuration Management tool of choice
- Docker 1.12+
- Wordpress official Docker image https://hub.docker.com/_/wordpress/
- Prometheus
- cAdvisor
- Grafana

In developing the solution, use GitHub/BitBucket and try to keep a decent commit history of how you approached the project.

## Deliverables

A Git repo with

- the Configuration Management Tool of Choice configs,
- Dockerfiles and Docker compose files
- shell script(s)
- Launch the AWS infrastructure with EC2 servers.
- Begin the configuration management / bootstrapping of the server. - Deploy the Prometheus stack.
- Finally start the blogging app as a Docker process. DO NOT CHECK THIS INTO GITHUB WITH AWS KEYS

---

## Braindump, write up later

### Points for CM

 - docker-compose is python, ansible is python, and ansible supports docker-compose in almost identical syntax so easy to port

### Points for Provisioner

 - aim is for reproduceabilty and demonstrable
 - no need for complexity like terraform, no "site" to deploy, only a single "development machine" (with security groups, etc)
 - ansible supports ec2 with idempotency, count_tags.
