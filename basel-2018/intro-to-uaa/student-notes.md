# Introduction to Cloud Foundry UAA

## Introduction

The Cloud Foundry UAA (User Account & Authentication) was created for Cloud Foundry Application Runtime itself, but its influence has broadened to BOSH, CredHub, Concourse, and a growing beyond the Cloud Foundry ecosystem. Your own applications can use the UAA to authenticate your users, and authorize selective behaviour, including bridging to federated user directories such as ActiveDirectory; and applications can use the UAA to authorize access between each other.

In this 30 minute lab we will be doing the following:

* Run the UAA locally (or upon a jumpbox) using [Quaa - Quick UAA](https://github.com/starkandwayne/quaa)
* Progressively enhance some a sample application with UAA authorization

## Learning Objectives

1. The UAA is a simple Java application that runs within an environment such as Apache Tomcat, or with the Cloud Foundry Java Buildpack. It has an in-memory database; but supports PostgreSQL and MySQL for long-term data persistence.
1. The UAA has a web UI for users to login, grant authorization to client applications to their data, revoke authorization grants, and perform multi-factor authentication
1. The UAA has an HTTP API to act as an OAuth2 Authorization Server, an OpenID Connect user information provider, and for clients to configure the UAA itself (create/modify/delete new clients, users, etc).
1. Backend APIs, called Resource Servers, can delegate authentication and authorization to the UAA.
1. Client applications, such as user-facing web apps or CLIs, pass access tokens to resource servers. They do not necessarily know identity information about their human user or another application client.
1. All applications can be written in any programming language and hosted anywhere. The OAuth2 standard is well recognized and client libraries exist everywhere.

## Prerequisites

To run the UAA locally requires:

1. Java 8 / Java 1.8

    ```plain
    $ java -version
    java version "1.8.0_66"
    ```

1. [Quick UAA Local](https://github.com/starkandwayne/quick-uaa-local/) project cloned:

    ```plain
    git clone https://github.com/starkandwayne/quick-uaa-local ~/workspace/quick-uaa-local
    cd ~/workspace/quick-uaa-local
    ```

To run the example applications requires:

1. Docker CLI and Docker Daemon running

    ```plain
    $ docker version
    Client:
     Version:           18.06.1-ce
      ...
    Server:
     Engine:
      Version:          18.06.1-ce
      ...
    ```

1. Example application source code:

    ```plain
    git clone https://github.com/starkandwayne/ultimate-guide-to-uaa-examples ~/workspace/ultimate-guide-to-uaa-examples
    ```

## Lab

## Learning Objectives Review

## Beyond the Lab