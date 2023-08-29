# A docker image for Specmatic

This repo contains a Docker build file for Specmatic. It also contains an example OpenAPI document.

To run with the example:

    git clone https://github.com/RamSailopal/Specmatic.git
    cd Specmatic/Example
    alias specmatic="docker run --rm -it -v "$PWD:/home/Example" ramb0/specmatic"
    alias specmatic-serv="docker run --rm -it -p 9000:9000 -v "$PWD:/home/Example" ramb0/specmatic"
    
To run the stub command with the process listening on port 9000, use:

    specmatic-serv stub

To run all other processes i.e test, use:

    specmatic test

## References

Specmatic - https://github.com/znsio/specmatic-documentation

OpenAPI - https://www.openapis.org/

