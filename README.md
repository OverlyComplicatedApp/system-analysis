# Overly Complicated App - System Analysis

This repository holds the artifacts with the requirements for the TODO list app being developed.

## Block Diagram

The [block diagram](block-diagram.svg) shows an overview of how the whole project will be organized.

There will be two microservices, one in Python and the other in Java, each of which will have its own dedicated database (PostgreSQL and MongoDB, respectively) and will sit inside separate docker containers.

The apps (browser, mobile and desktop) will only see and call the API Gateway, which will be responsible for calling the proper microservices.

## Use cases

The written [use cases](use-cases.md) give an idea of the project's scope in a descriptive manner. They show what the requirements are and what's expected from the app.

## Mockups

The [mockups](mockups/) were created to complement the use cases and to give a general idea of how the mobile version of the app should look like.
