# Microservices

A microservice is a design approach in software development where an application is structured as a collection of loosely coupled, independently deployable services. Each microservice focuses on a specific business function and communicates with other microservices through well-defined APIs. This architectural style enhances scalability, flexibility, and maintainability, as individual services can be developed, deployed, and scaled independently. By breaking down an application into smaller, manageable pieces, teams can work more autonomously and implement updates or fixes without affecting the entire system. This approach contrasts with monolithic architectures, where all components are interwoven into a single, large application.

Can work on one section of the application without having to take the entire thing down. E.g if just the click and collect section didn't work

monolith best when the set use/requirements don't change like a school with 200 students.

if the same school wanted to open more branches and needed to use the same app that inital 200 is going to multiply exponentially could I refactor into two tier or microservices.

Microserveries need more teams to manage and is going to cost more money. can be hard to manage on a large scale

Build docker

Manage maintain scale K8 (Kubernetes)

can contreraise our app into microservice, another microserver could be the mongodb another could be the log in.

no relational db any sort of data relational need to provide the adress/info it is using

we will host our microservices (docker images) on docker hub

mservice something that has a singular end point

container is a running instance that has it's own id/endpoint that we can communcate with

hosts our files globall, docker pull will clone a repo to m machine if it's public you need the tag similar to github but the account name matters need to put the account id and the specific repo

