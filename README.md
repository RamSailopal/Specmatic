# A docker image for Specmatic

![example workflow](https://github.com/RamSailopal/Specmatic/actions/workflows/docker.yml/badge.svg)

This repo contains a Docker build file for Specmatic as well as examples with local and remote OpenAPI files. 

## Setup

To set up a Dockerised Specmatic environment locally, run:

    git clone https://github.com/RamSailopal/Specmatic.git
    cd Specmatic/Example
    alias specmatic="docker run --rm -it -v "$PWD:/home/Example" ramb0/specmatic"
    alias specmatic-serv="docker run --rm -it -p 9000:9000 -v "$PWD:/home/Example" ramb0/specmatic"

## Local OpenAPI file

An example OpenAPI file for a simple pets API has been created  - **Example/service.yaml** Another file for "canned responses" has been also been created - **Example/scooby.json** 

To run a "stub server" for the API on port 9000, run:

     specmatic-serv stub service.yaml

To test the API, you first need the local network accessible IP address of the host machine:

Linux -

    ip add show

Windows -

    ipconfig

Once this has been attained, run:

     specmatic test service.yaml --host <addressofhostmachine>

i.e.

     specmatic test --host 172.28.61.122 

## OpenAPI file stored in a separate centralised repo

References to a centralised repo can be made in the setup through the file **Example/specmatic.json**

As an example, references to an openAPI file in the Specmatic repo have been made - https://github.com/znsio/specmatic-order-contracts/blob/main/in/specmatic/examples/store/api_order_v1.yaml

When running Specmatic with a specmatic.json configured, there is no need to specify the location of the local OpenAPI file and so, to run the stub command with the process listening on port 9000, use:

    specmatic-serv stub

To run all other processes i.e test, use:

    specmatic test --host <addressofmachine>

## References

**Docker Hub** - https://hub.docker.com/repository/docker/ramb0/specmatic/general

**Specmatic** - https://github.com/znsio/specmatic-documentation

**OpenAPI** - https://www.openapis.org/

