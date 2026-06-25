#!/bin/bash

# Part 3 - Black Hat Bash Lab

## Description

This part of the project consisted of deploying the Black Hat Bash vulnerable laboratory using Docker and Docker Compose. The environment was executed locally inside a virtual machine and isolated from external networks.

---

## Deployment

The following commands were used to deploy and verify the laboratory:

```bash
sudo make deploy
sudo make test
```

The deployment process downloaded the required Docker images, created the containers, configured the networks, and prepared the vulnerable environment.

---

## Verification

The laboratory was verified successfully using:

```bash
sudo make test
```

Expected result:

```text
Lab is up.
```

This confirms that all services and containers were running correctly.

---

## Containers

The laboratory consists of eight Docker containers distributed across two networks.

Example containers:

| Container   | Purpose                      |
| ----------- | ---------------------------- |
| p-web-01    | Public web server            |
| p-web-02    | Secondary public web server  |
| p-ftp-01    | Public FTP server            |
| c-client-01 | Corporate client workstation |
| c-client-02 | Corporate client workstation |
| c-db-01     | Corporate database server    |
| c-file-01   | Corporate file server        |
| c-admin-01  | Administrative workstation   |

The containers simulate a small corporate environment with both public-facing and internal systems.

---

## Networks

The lab uses two isolated Docker networks:

### Public Network

```text
172.16.10.0/24
```

Bridge interface:

```text
br_public
```

This network contains internet-facing services such as web and FTP servers.

### Corporate Network

```text
10.1.0.0/24
```

Bridge interface:

```text
br_corporate
```

This network contains internal corporate systems and services.

---

## Architecture

| Hostname    | Public IP    | Corporate IP |
| ----------- | ------------ | ------------ |
| p-web-01    | 172.16.10.10 | -            |
| p-web-02    | 172.16.10.11 | -            |
| p-ftp-01    | 172.16.10.12 | -            |
| c-client-01 | -            | 10.1.0.10    |
| c-client-02 | -            | 10.1.0.11    |
| c-db-01     | -            | 10.1.0.20    |
| c-file-01   | -            | 10.1.0.21    |
| c-admin-01  | -            | 10.1.0.30    |

The architecture separates public services from internal corporate resources using two different Docker networks.

---

## Evidence

The following screenshots were collected during the deployment and verification process:

* Successful execution of `sudo make deploy`
* Successful execution of `sudo make test`
* Output of `sudo docker ps`
* Output of `ip addr`
* Verification of `br_public`
* Verification of `br_corporate`
* Access to a container using:

```bash
sudo docker exec -it p-web-01 bash
```

* Hostname verification inside the container

```bash
hostname
```

---

## Result

The Black Hat Bash Lab was deployed successfully using Docker and Docker Compose. All containers were operational, network connectivity was verified, and the environment was ready for security testing and reconnaissance activities.
